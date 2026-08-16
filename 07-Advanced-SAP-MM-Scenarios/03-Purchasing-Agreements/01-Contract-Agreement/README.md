# Contract Agreements

## Overview

Contract Agreements in SAP S/4HANA MM are long-term purchasing agreements used to manage recurring procurement requirements between an organization and its suppliers.

In this project, Contract Agreements are demonstrated using **UMECO** as the supplier and **SMT Wipe Roll** as the manufacturing consumable.

Two types of Contract Agreements are covered:

- Quantity Contract
- Value Contract

Both contracts are created using **ME31K** and are followed by the common procurement process documented separately under `02-Contract-Procurement-Process`.

---

## Business Scenario

The organization regularly requires SMT Wipe Roll for manufacturing activities and purchases the material from UMECO.

Instead of managing every requirement independently, a long-term purchasing agreement is established with the supplier.

The project demonstrates two different ways of controlling this long-term procurement commitment.

```text
UMECO
  |
  v
SMT Wipe Roll
  |
  +-------------------------+
  |                         |
  v                         v
Quantity Contract       Value Contract
  |                         |
  v                         v
10,000 EA               ₹5,00,000
The Quantity Contract is used when the organization wants to control procurement based on an agreed quantity.

The Value Contract is used when the organization wants to control procurement based on an agreed monetary value.

Quantity Contract

A Quantity Contract is a long-term purchasing agreement where the primary commitment is based on a predefined quantity.

Example:

Field	Details
Supplier	UMECO
Material	SMT Wipe Roll
Contract Type	Quantity Contract
Target Quantity	10,000 EA
Transaction	ME31K

The purchasing team can monitor how much quantity has been consumed against the agreed contract quantity.

Contract Quantity
       |
       v
10,000 EA
       |
       v
Procurement
       |
       v
Quantity Consumed
       |
       v
Remaining Quantity

Detailed Quantity Contract creation and validation are documented in:

Quantity-Contract.md

Value Contract

A Value Contract is a long-term purchasing agreement where the primary commitment is based on a predefined monetary value.

Example:

Field	Details
Supplier	UMECO
Material	SMT Wipe Roll
Contract Type	Value Contract
Target Value	₹5,00,000
Transaction	ME31K

The purchasing team can monitor procurement expenditure against the agreed contract value.

Contract Value
       |
       v
₹5,00,000
       |
       v
Procurement
       |
       v
Value Consumed
       |
       v
Remaining Value

Detailed Value Contract creation and validation are documented in:

Value-Contract.md

Contract Agreement Process

Both Quantity Contracts and Value Contracts use the same downstream procurement process after the agreement is established.

The common process is maintained separately under:

02-Contract-Procurement-Process

Contract Agreement
        |
        v
Purchase Requisition
      ME51N
        |
        v
Purchase Order
      ME21N
        |
        v
Goods Receipt
       MIGO
        |
        v
Stock Verification
       MMBE
        |
        v
Invoice Verification
       MIRO

The Contract Agreement therefore establishes the long-term purchasing framework, while the subsequent PR, PO, Goods Receipt, inventory verification, and invoice verification activities execute the actual procurement requirement.

Quantity Contract vs Value Contract
Feature	Quantity Contract	Value Contract
Supplier	UMECO	UMECO
Material	SMT Wipe Roll	SMT Wipe Roll
Primary Control	Quantity	Monetary Value
Example	10,000 EA	₹5,00,000
SAP Creation	ME31K	ME31K
Main Objective	Control quantity	Control expenditure

The key difference is:

Quantity Contract → Controls HOW MUCH material can be procured.


Value Contract → Controls HOW MUCH can be spent.