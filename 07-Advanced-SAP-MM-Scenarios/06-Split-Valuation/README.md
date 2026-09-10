# Split Valuation – SAP S/4HANA MM

## 01. Introduction

**Split Valuation** in SAP S/4HANA MM allows the same material to be managed as separate partial stocks based on different valuation types.

In this project, the material **`COPPER_WIRE`** was used to demonstrate split valuation for two procurement sources:

- **`NT-IN`** – Internal Procurement
- **`NT-EX`** – External Procurement

The scenario demonstrates how SAP maintains separate stock and valuation information for the same material while keeping the stock within the same plant and storage location.

---

## 02. Business Scenario

**Company:** Novatech Electronics Pvt. Ltd.  
**Plant:** `CN01`  
**Storage Location:** `CS01 – Consumables ST`  
**Material:** `COPPER_WIRE`  
**Material Type:** `ROH`  
**Base Unit:** `KG`

The business requires different valuation for copper wire depending on its procurement source.

| Valuation Type | Procurement Source | Quantity | Valuation Price |
|---|---|---:|---:|
| `NT-IN` | Internal Procurement | 100 KG | ₹80/KG |
| `NT-EX` | External Procurement | 100 KG | ₹100/KG |
| **Total** | **Combined Stock** | **200 KG** | **Separate Valuation** |

This provides clear visibility of internally and externally sourced stock without creating separate material numbers.

---

## 03. Split Valuation Process

The complete scenario was executed through the following process:

```text
Split Valuation Configuration
          ↓
COPPER_WIRE Material
          ↓
Valuation Type NT-IN
          ↓
Internal Procurement
          ↓
100 KG Internal Stock
          ↓
Valuation Type NT-EX
          ↓
External Purchase Order
          ↓
MIGO – Goods Receipt
          ↓
100 KG External Stock
          ↓
MIRO – Invoice Verification
          ↓
MMBE – Final Stock Analysis
          ↓
Split Stock Successfully Validated
```

### Main Activities

1. Configure/activate split valuation.
2. Maintain valuation category and valuation types.
3. Create/extend `COPPER_WIRE` with split valuation.
4. Create internal valuation stock using `NT-IN`.
5. Create external procurement using `NT-EX`.
6. Create external PO `4500002303`.
7. Post external goods receipt through `MIGO`.
8. Post supplier invoice through `MIRO`.
9. Verify stock using `MMBE`.
10. Perform final split-stock testing.

---

## 04. Procurement, MIGO, MIRO & Stock Analysis

### Internal Procurement

The internal procurement scenario created:

**Material:** `COPPER_WIRE`  
**Valuation Type:** `NT-IN`  
**Quantity:** `100 KG`  
**Price:** `₹80/KG`

The stock was posted to:

`CN01 → CS01 → NT-IN`

The stock analysis confirmed **100 KG** under the internal valuation type.

### External Procurement

The external procurement scenario used:

**Supplier:** `7000010015 – JUSDA CORPORATIONS PVT LTD`  
**PO:** `4500002303`  
**Material:** `COPPER_WIRE`  
**Quantity:** `100 KG`  
**Price:** `₹100/KG`  
**Valuation Type:** `NT-EX`

The goods receipt was posted through **MIGO** using movement type `101`.

The invoice was then processed through **MIRO**.

The PO history confirmed the completed procurement cycle:

`PO → Goods Receipt → Invoice Receipt`

---

## 05. Final Result & Testing

The final testing confirmed that SAP maintained the same material with separate valuation types.

| Validation | Result |
|---|---|
| `COPPER_WIRE` material | PASS |
| Internal valuation `NT-IN` | 100 KG – PASS |
| External valuation `NT-EX` | 100 KG – PASS |
| Total stock | 200 KG – PASS |
| Separate valuation maintained | PASS |
| External PO `4500002303` | PASS |
| MIGO Goods Receipt | PASS |
| MIRO Invoice Verification | PASS |
| MMBE Stock Analysis | PASS |

### Final Stock Position

```text
COPPER_WIRE
│
├── NT-IN – Internal Procurement
│   └── 100 KG
│
└── NT-EX – External Procurement
    └── 100 KG

Total Stock = 200 KG
```

### Conclusion

The Split Valuation scenario successfully demonstrated how SAP S/4HANA MM can maintain **different valuation types for the same material** based on procurement source.

The project covered:

**Configuration → Material Valuation → Internal Stock → External PO → MIGO → MIRO → MMBE → Testing**

This scenario demonstrates practical understanding of **SAP MM inventory valuation, procurement integration, goods receipt, invoice verification, and stock analysis**.

### SAP Transactions Used

| Transaction | Purpose |
|---|---|
| `ME51N` | Purchase Requisition |
| `ME21N` | Purchase Order |
| `MIGO` | Goods Receipt |
| `MIRO` | Invoice Verification |
| `ME23N` | Purchase Order History |
| `MMBE` | Stock Overview |
