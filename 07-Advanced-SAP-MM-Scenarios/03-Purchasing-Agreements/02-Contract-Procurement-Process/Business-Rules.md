# Business Rules – Purchasing Agreements

## 1. Overview

Business Rules define the controls and conditions that govern how Purchasing Agreements are created and used during the procurement process.

The rules ensure that procurement is performed within the approved contract quantity or value and that subsequent Purchase Orders follow the agreed purchasing terms.

---

## 2. Quantity Contract – MK

A **Quantity Contract (MK)** controls procurement based on a predefined target quantity.

### Business Rules

- The contract must have a defined validity period.
- A supplier must be assigned to the contract.
- Material and purchasing information must be maintained.
- The Release PO must be created with reference to the contract.
- The total quantity released through POs should not exceed the contract target quantity.
- SAP validates the available contract quantity during the release process.
- If the target quantity is exceeded, SAP displays a quantity-exceeded message.

**Control:**

`Contract Target Quantity → Release PO Quantity → SAP Quantity Validation`

---

## 3. Value Contract – WK

A **Value Contract (WK)** controls procurement based on a predefined target monetary value.

### Business Rules

- The contract must have a defined validity period.
- A supplier must be assigned to the contract.
- The applicable purchasing information must be maintained.
- Release POs should be created with reference to the value contract.
- The total release value should not exceed the contract target value.
- SAP validates the available contract value during the release process.
- If the target value is exceeded, SAP displays a value-exceeded message.

**Control:**

`Contract Target Value → Release PO Value → SAP Value Validation`

---

## 4. Goods Receipt Rules

After the Release PO is created:

- Goods Receipt is performed using **MIGO**.
- The Goods Receipt is created with reference to the Purchase Order.
- Movement Type **101** is used for standard Goods Receipt.
- The received quantity must be verified before posting.
- The material is posted to the relevant Plant and Storage Location.
- Successful posting creates a Material Document.

---

## 5. Overall Business Rule

The complete procurement process follows:

`Purchasing Agreement → Release PO → Contract Validation → Goods Receipt → Material Document → Invoice Verification`

These rules provide controlled procurement, prevent excessive releases against agreements, and maintain traceability throughout the procurement cycle.