# Business Rules – Scheduling Agreement

## 1. Agreement Validity

* A Scheduling Agreement must have a valid **start date and end date**.
* Procurement activities must be performed only within the agreement validity period.
* The agreement should be reviewed or extended before the validity period expires if further procurement is required.

---

## 2. Supplier and Organizational Data

* The Scheduling Agreement must be created for an approved supplier.
* The correct **Company Code, Purchasing Organization, Purchasing Group, Plant, and Storage Location** must be maintained.
* Supplier and organizational data must be validated before saving the agreement.

---

## 3. Material and Quantity Control

* Only valid and approved materials should be maintained in the Scheduling Agreement.
* The **Target Quantity** must represent the approved procurement requirement.
* Goods Receipt quantities must follow the quantities defined in the delivery schedule.
* Total scheduled quantities should not exceed the agreed target quantity unless an authorized change is made.

---

## 4. Delivery Schedule Control

* Delivery dates and quantities must be maintained through `ME38`.
* Each schedule line defines the expected delivery date and quantity.
* Goods Receipt should be processed according to the applicable schedule line.
* If a delivery is attempted before the scheduled date, SAP may prevent the schedule line from being selected based on system configuration and delivery controls.

---

## 5. Goods Receipt and Invoice Verification

* Goods Receipt must be posted using movement type `101` against the Scheduling Agreement.
* The received quantity must correspond to the applicable scheduled quantity.
* Invoice Verification through `MIRO` should be performed only after the relevant Goods Receipt has been completed.
* Invoice quantity and amount must be verified against the Scheduling Agreement and Goods Receipt before posting.

---

## 6. Authorization and Document Control

* Scheduling Agreement creation and changes must follow the organization's approval and authorization procedures.
* Changes to supplier, material, quantity, price, validity, or delivery schedule must be properly authorized.
* All Scheduling Agreement, Goods Receipt, and Invoice documents must be retained for audit and traceability.
* The Scheduling Agreement number must be used to maintain a clear link between the agreement, delivery schedule, Goods Receipt, and invoice.
