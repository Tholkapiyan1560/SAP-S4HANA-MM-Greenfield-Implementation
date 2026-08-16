# 03 – Scheduling Agreement – Testing

## 1. Scheduling Agreement Creation Test

### Transaction Code

`ME31L`

The Scheduling Agreement is created with a target quantity of **14,000 EA**.

| Field                   | Test Value     |
| ----------------------- | -------------- |
| Agreement Type          | LP             |
| Supplier                | 7000010015     |
| Company Code            | NT01           |
| Purchasing Organization | POR1           |
| Purchasing Group        | CS0            |
| Plant                   | CN01           |
| Storage Location        | CS01           |
| Material                | BARE_PCB_BOARD |
| Target Quantity         | 14,000 EA      |
| Net Price               | 500.00 INR     |
| Validity Start          | 16.08.2026     |
| Validity End            | 15.08.2027     |

**Expected Result:** Scheduling Agreement should be created successfully.

**Scheduling Agreement:** `7000000016`

---

## 2. Delivery Schedule Test

### Transaction Code

`ME38`

The total quantity of **14,000 EA** is divided into two schedule lines.

| Delivery Date | Scheduled Quantity |
| ------------- | -----------------: |
| 16.08.2026    |           7,000 EA |
| 31.08.2026    |           7,000 EA |
| **Total**     |      **14,000 EA** |

**Expected Result:** The total scheduled quantity should match the target quantity of the Scheduling Agreement.

---

## 3. First Goods Receipt Test

### Transaction Code

`MIGO`

The first scheduled delivery is processed against Scheduling Agreement `7000000016`.

* Scheduled Date: `16.08.2026`
* Quantity: `7,000 EA`
* Movement Type: `101`
* Plant: `CN01`
* Storage Location: `CS01`

**Expected Result:** SAP should allow the first scheduled quantity of **7,000 EA** to be received and posted successfully.

---

## 4. Future Delivery Date Validation Test

The second schedule line is maintained for:

**31.08.2026 → 7,000 EA**

An attempt is made to process the second delivery before the scheduled delivery date.

**Expected Result:** The second schedule line should not be available for selection before its scheduled date, depending on the configured delivery controls.

This test confirms that the Scheduling Agreement delivery schedule controls the planned Goods Receipt.

---

## 5. Second Goods Receipt Test

### Transaction Code

`MIGO`

On the scheduled date of **31.08.2026**, the second delivery is processed.

* Scheduling Agreement: `7000000016`
* Material: `BARE_PCB_BOARD`
* Quantity: `7,000 EA`
* Movement Type: `101`
* Posting Date: `31.08.2026`

**Expected Result:** The second Goods Receipt should be posted successfully.

### Quantity Validation

```text
First Goods Receipt  = 7,000 EA
Second Goods Receipt = 7,000 EA
--------------------------------
Total Received       = 14,000 EA
```

---

## 6. Invoice Verification Test

### Transaction Code

`MIRO`

The supplier invoice is processed with reference to Scheduling Agreement `7000000016`.

| Field                | Value            |
| -------------------- | ---------------- |
| Scheduling Agreement | 7000000016       |
| Material             | BARE_PCB_BOARD   |
| Invoice Quantity     | 7,000 EA         |
| Base Amount          | 3,500,000.00 INR |
| Tax Amount           | 630,000.00 INR   |
| Total Invoice Amount | 4,130,000.00 INR |

**Expected Result:** SAP should retrieve the relevant purchasing information and allow the invoice to proceed for verification.

---

## 7. Invoice Simulation Test

Before posting the invoice, the **Simulate** function is used in MIRO.

The accounting entries are reviewed to confirm that the invoice is balanced.

```text
Debit  = 4,130,000.00 INR
Credit = 4,130,000.00 INR
Balance = 0.00 INR
```

**Expected Result:** The invoice should be successfully simulated with a balance of `0.00 INR`.

---

## 8. Final Process Validation

The complete Scheduling Agreement process is validated as follows:

```text
ME31L
   ↓
Create Scheduling Agreement
   ↓
Target Quantity = 14,000 EA
   ↓
Agreement No. 7000000016
   ↓
ME38
   ↓
16.08.2026 → 7,000 EA
31.08.2026 → 7,000 EA
   ↓
MIGO
   ↓
First GR → 7,000 EA
   ↓
Future Delivery Validation
   ↓
Second GR → 7,000 EA
   ↓
Total GR → 14,000 EA
   ↓
MIRO
   ↓
Invoice Verification
   ↓
Simulate
   ↓
Balance = 0.00 INR
   ↓
Post Invoice
   ↓
Process Completed
```

### Final Test Result

| Test Area                     | Result     |
| ----------------------------- | ---------- |
| Scheduling Agreement Creation | Passed     |
| Delivery Schedule             | Passed     |
| First Goods Receipt           | Passed     |
| Future Delivery Validation    | Passed     |
| Second Goods Receipt          | Passed     |
| Invoice Verification          | Passed     |
| Invoice Simulation            | Passed     |
| Complete Process              | **Passed** |

**Overall Testing Status: PASSED**
