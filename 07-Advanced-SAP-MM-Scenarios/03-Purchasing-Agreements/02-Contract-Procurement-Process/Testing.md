# Testing – Purchasing Agreements

## 1. Overview

Testing is performed to verify that the Purchasing Agreement process works according to the defined business rules.

The testing covers both **Quantity Contracts (MK)** and **Value Contracts (WK)**, including:

- Contract validation
- Release Purchase Order creation
- Goods Receipt
- Invoice Verification

---

## 2. Quantity Contract Testing

### Test Scenario

Verify that a Release PO can be created against a Quantity Contract and that SAP controls the contract target quantity.

### Test Steps

1. Create or use the Quantity Contract.
2. Create a Release PO using **ME21N** with reference to the contract.
3. Verify the contract material, supplier, price and quantity.
4. Create a release within the available contract quantity.
5. Attempt to exceed the remaining contract quantity.
6. Verify the SAP validation message.
7. Post the Goods Receipt using **MIGO**.
8. Perform Invoice Verification using **MIRO**.

### Expected Result

- Release PO is successfully created within the available quantity.
- SAP validates the contract when the target quantity is exceeded.
- Goods Receipt is successfully posted using **Movement Type 101**.
- Material Document is created.
- Invoice can be verified against the Purchase Order and Goods Receipt.

---

## 3. Value Contract Testing

### Test Scenario

Verify that a Release PO can be created against a Value Contract and that SAP controls the contract target value.

### Test Steps

1. Create or use the Value Contract.
2. Create a Release PO using **ME21N** with reference to the contract.
3. Verify the supplier, material and purchasing information.
4. Create a release within the available contract value.
5. Attempt to exceed the remaining contract value.
6. Verify the SAP validation message.
7. Post the Goods Receipt using **MIGO**.
8. Perform Invoice Verification using **MIRO**.

### Expected Result

- Release PO is successfully created within the available value.
- SAP validates the contract when the target value is exceeded.
- Goods Receipt is successfully posted using **Movement Type 101**.
- Material Document is created.
- Invoice can be verified against the Purchase Order and Goods Receipt.

---

## 4. Goods Receipt Testing – MIGO

### Test Scenario

Verify that Goods Receipt can be successfully posted against the Release Purchase Order.

### Test Steps

1. Open **MIGO**.
2. Select **Goods Receipt**.
3. Select **Purchase Order** as the reference.
4. Enter the Release PO number.
5. Verify material and received quantity.
6. Use **Movement Type 101**.
7. Verify Plant, Storage Location and Stock Type.
8. Post the Goods Receipt.
9. Verify the generated Material Document.

### Expected Result

- Purchase Order details are retrieved successfully.
- Received quantity is correctly entered.
- Movement Type 101 is used.
- Goods Receipt is successfully posted.
- SAP creates a Material Document.
- Inventory is updated accordingly.

---

## 5. Invoice Verification Testing – MIRO

### Test Scenario

Verify that the supplier invoice can be processed against the Purchase Order and Goods Receipt using **MIRO**.

### Test Steps

1. Open **MIRO – Enter Incoming Invoice**.
2. Select the appropriate invoice transaction.
3. Enter the relevant Purchase Order number as the reference.
4. Verify the supplier, invoice amount and invoice quantity.
5. Check the Purchase Order and Goods Receipt information.
6. Verify that the invoice values are within the applicable tolerances.
7. Simulate or check the invoice.
8. Post the Invoice Verification document.

### Expected Result

- Purchase Order information is retrieved successfully.
- Supplier and invoice details are verified.
- Invoice quantity and value are checked against the procurement documents.
- The invoice passes the applicable SAP checks and tolerances.
- Invoice Verification is successfully posted.
- An Invoice Document is created.

---

## 6. End-to-End Testing

The complete Purchasing Agreement procurement cycle is tested as follows:

```text
Purchasing Agreement
        │
        ▼
Release Purchase Order
       ME21N
        │
        ▼
Contract Validation
        │
        ▼
Goods Receipt
       MIGO
        │
        ▼
Material Document
        │
        ▼
Invoice Verification
       MIRO
        │
        ▼
Invoice Document

