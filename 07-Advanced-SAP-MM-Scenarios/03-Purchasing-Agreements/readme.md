# Purchasing Agreements

## Overview

Purchasing Agreements in SAP S/4HANA Materials Management (MM) are used to establish and manage long-term procurement relationships between an organization and its suppliers.

In a manufacturing organization, several materials are required repeatedly throughout the year. These requirements may include production materials, manufacturing consumables, electronic components, engineering materials, spare parts, and other operational materials.

When the same material is repeatedly purchased from the same supplier, creating a completely independent purchasing arrangement for every requirement can increase the workload of the purchasing team and make it difficult to monitor the overall supplier commitment.

SAP S/4HANA MM provides Purchasing Agreements to manage such recurring and long-term procurement requirements in a structured manner.

A Purchasing Agreement provides a framework between the purchasing organization and supplier for future procurement. Depending on the business requirement, the organization can control the agreement based on quantity, monetary value, or planned delivery schedules.

The Purchasing Agreements covered in this project are:

- Contract Agreement
- Quantity Contract
- Value Contract
- Scheduling Agreement

---

## Purchasing Agreement Structure

```text
Purchasing Agreements
        |
        +--------------------------+
        |                          |
        v                          v
Contract Agreement        Scheduling Agreement
        |
   +----+----+
   |         |
   v         v
Quantity    Value
Contract    Contract
The project demonstrates these scenarios using realistic manufacturing procurement examples.

Contract Agreement Scenario
Field	Details
Supplier	UMECO
Material	SMT Wipe Roll
Agreement Types	Quantity Contract, Value Contract

SMT Wipe Roll is considered a manufacturing consumable that can be required repeatedly during manufacturing and operational activities.

Scheduling Agreement Scenario
Field	Details
Supplier	JUSDA CORPORATIONS PVT LTD
Material	BARE_PCB_BOARD
Plant	CN01
Storage Location	CS01

BARE_PCB_BOARD represents a recurring manufacturing material for which planned quantities and delivery dates are important.

Business Requirement

The organization has recurring procurement requirements for manufacturing materials and consumables.

Some materials are purchased continuously from established suppliers. These materials may have predictable requirements over a period of time, while other materials may require planned deliveries according to production schedules.

For example, SMT Wipe Roll may be required repeatedly by the manufacturing operation.

The organization already has a supplier relationship with UMECO and expects to procure the material from the supplier during a defined period.

Instead of treating every requirement as an independent purchasing activity, the organization can establish a long-term Contract Agreement.

The Contract Agreement can then be controlled based on either:

Total quantity
Total purchasing value

Therefore, two different Contract scenarios are demonstrated:

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
Quantity Control        Value Control

A different requirement exists for BARE_PCB_BOARD.

The organization requires this material regularly for manufacturing operations and needs the supplier to deliver the material according to planned dates and quantities.

For this requirement, a Scheduling Agreement is more appropriate because the purchasing organization needs to maintain a delivery schedule.

JUSDA CORPORATIONS PVT LTD
            |
            v
      BARE_PCB_BOARD
            |
            v
   Scheduling Agreement
            |
            v
       Schedule Lines
            |
            v
    Delivery Dates + Quantities

The overall business requirement is therefore:

Recurring Procurement Requirement
              |
              v
       Long-Term Supplier
          Relationship
              |
              v
      Purchasing Agreement
              |
        +-----+-----+
        |           |
        v           v
     Contract    Scheduling
     Agreement   Agreement
        |
    +---+---+
    |       |
    v       v
 Quantity  Value
 Contract  Contract

The agreement type should be selected according to the actual business requirement rather than simply selecting one agreement type for every procurement scenario.

Purpose of Purchasing Agreements

The purpose of Purchasing Agreements is to provide a structured method for managing long-term procurement requirements.

Purchasing Agreements help the organization establish a long-term relationship with suppliers and provide a framework for future procurement.

The major objectives are:

Establish long-term supplier relationships.
Define procurement commitments.
Reduce repetitive purchasing activities.
Improve supplier coordination.
Control purchasing quantities.
Control purchasing expenditure.
Plan recurring material deliveries.
Improve material availability.
Improve procurement visibility.
Support production planning.
Monitor procurement against agreed commitments.
Improve purchasing control.

The Purchasing Agreement therefore becomes an important part of the procurement process when the organization has recurring requirements from the same supplier.

Contract Agreement
Overview

A Contract Agreement is a long-term purchasing agreement between an organization and a supplier.

The agreement is valid for a defined period and provides a framework for future procurement.

A Contract Agreement is useful when the organization knows that it will repeatedly purchase materials or services from the same supplier during a specific period.

The contract establishes the long-term purchasing relationship, while subsequent procurement activities are executed against the agreed arrangement.

In this project, the Contract Agreement scenario uses:

Field	Details
Supplier	UMECO
Material	SMT Wipe Roll

The business requirement is to establish a long-term purchasing relationship with UMECO for SMT Wipe Roll.

The organization expects repeated requirements for the material and therefore wants to avoid treating every requirement as a completely independent purchasing activity.

The Contract Agreement can be controlled using two approaches:

Contract Agreement
        |
        +-------------------+
        |                   |
        v                   v
Quantity Contract       Value Contract
        |                   |
        v                   v
Quantity Control       Value Control
Quantity Contract
Overview

A Quantity Contract is a Contract Agreement in which the primary commitment is based on a predefined quantity.

The organization and supplier agree on the quantity that can be procured during the validity period of the contract.

The purchasing team can then monitor how much quantity has been consumed and how much remains available.

For this project, the Quantity Contract scenario is based on:

Field	Details
Supplier	UMECO
Material	SMT Wipe Roll
Agreement Type	Quantity Contract
Agreed Quantity	10,000 EA
Validity	01.01.2026 – 31.12.2026

The primary business objective is to control the total quantity purchased against the agreement.

Quantity Contract Example
Description	Quantity
Total Contract Quantity	10,000 EA
Consumed Quantity	2,000 EA
Remaining Quantity	8,000 EA

If additional procurement is executed, the consumed quantity increases and the remaining quantity decreases.

For example:

Initial Contract
10,000 EA
     |
     v
First Procurement
2,000 EA
     |
     v
Remaining
8,000 EA
     |
     v
Second Procurement
1,500 EA
     |
     v
Remaining
6,500 EA

The purchasing team can therefore monitor the contract utilization.

The overall concept is:

Agreed Quantity
       |
       v
Procurement Requirement
       |
       v
Procurement Against Agreement
       |
       v
Quantity Consumed
       |
       v
Remaining Quantity

A Quantity Contract is suitable when the organization has a defined quantity requirement and wants to control procurement primarily through quantity.

Quantity Contract Business Scenario

The organization requires SMT Wipe Roll regularly for manufacturing activities.

The purchasing team evaluates the expected annual requirement and establishes a long-term procurement arrangement with UMECO.

The expected requirement is 10,000 EA.

Instead of negotiating the complete procurement arrangement every time a new requirement occurs, the purchasing organization establishes a Quantity Contract.

The contract provides a framework for future procurement.

Business Flow
Manufacturing Requirement
          |
          v
      SMT Wipe Roll
          |
          v
        UMECO
          |
          v
    Quantity Contract
          |
          v
       10,000 EA
          |
          v
   Future Procurement
          |
          v
   Quantity Consumption
          |
          v
Remaining Contract Quantity

This approach improves visibility of the total quantity commitment.

Value Contract
Overview

A Value Contract is a Contract Agreement in which the primary commitment is based on a predefined monetary value.

Instead of controlling the agreement mainly by quantity, the organization controls the total purchasing value.

For this project, the Value Contract scenario is:

Field	Details
Supplier	UMECO
Material	SMT Wipe Roll
Agreement Type	Value Contract
Contract Value	₹5,00,000
Validity	01.01.2026 – 31.12.2026

The organization establishes a maximum purchasing value for the agreement period.

The purchasing team can monitor the value already consumed and the remaining value.

Value Contract Example
Description	Amount
Total Contract Value	₹5,00,000
Consumed Value	₹1,50,000
Remaining Value	₹3,50,000

If another procurement activity consumes ₹75,000:

Description	Amount
Previous Remaining Value	₹3,50,000
Additional Consumption	₹75,000
New Remaining Value	₹2,75,000

The business concept is:

Agreed Contract Value
          |
          v
Procurement Requirement
          |
          v
Procurement Against Agreement
          |
          v
Value Consumed
          |
          v
Remaining Contract Value

A Value Contract is therefore suitable when the purchasing organization wants to control the total financial commitment rather than primarily controlling a fixed quantity.

Value Contract Business Scenario

The organization may have recurring requirements for SMT Wipe Roll, but the exact quantity may vary depending on manufacturing demand.

In such a scenario, controlling the total purchasing expenditure may be more useful than controlling a fixed quantity.

The purchasing team therefore establishes a Value Contract with UMECO for ₹5,00,000.

Business Flow
Manufacturing Requirement
          |
          v
      SMT Wipe Roll
          |
          v
        UMECO
          |
          v
      Value Contract
          |
          v
       ₹5,00,000
          |
          v
   Future Procurement
          |
          v
    Value Consumption
          |
          v
 Remaining Contract Value

This provides financial control over the long-term procurement relationship.

Quantity Contract vs Value Contract

Quantity Contracts and Value Contracts are both Contract Agreements. However, the primary control mechanism is different.

Feature	Quantity Contract	Value Contract
Supplier	UMECO	UMECO
Material	SMT Wipe Roll	SMT Wipe Roll
Primary Control	Quantity	Monetary Value
Example Commitment	10,000 EA	₹5,00,000
Main Objective	Control quantity	Control expenditure
Monitoring	Quantity consumed	Value consumed
Suitable For	Predictable quantity requirement	Variable quantity with spending control

The basic difference can be represented as:

Quantity Contract
        |
        v
How much material can be procured?
        |
        v
Quantity-Based Control

And:

Value Contract
        |
        v
How much can be spent?
        |
        v
Value-Based Control

Therefore, the purchasing organization must select the contract type according to the actual business requirement.

Scheduling Agreement
Overview

A Scheduling Agreement is a long-term purchasing arrangement used when the organization has recurring requirements and needs planned deliveries from a supplier.

The major difference is that the Scheduling Agreement focuses heavily on delivery scheduling.

Instead of simply establishing a long-term purchasing commitment, the organization maintains specific delivery requirements.

For this project, the Scheduling Agreement scenario uses:

Field	Details
Supplier	JUSDA CORPORATIONS PVT LTD
Material	BARE_PCB_BOARD
Plant	CN01
Storage Location	CS01

BARE_PCB_BOARD is considered a recurring manufacturing material.

The organization requires the material regularly and needs the supplier to deliver specific quantities on specific dates.

The Scheduling Agreement provides a structured mechanism for maintaining these planned requirements.

Scheduling Agreement Business Requirement

The organization has recurring requirements for BARE_PCB_BOARD.

Production planning determines that the material will be required at different points in time.

Instead of creating separate procurement arrangements for every requirement, the purchasing organization establishes a Scheduling Agreement with JUSDA CORPORATIONS PVT LTD.

The required deliveries are then maintained using schedule lines.

Process Flow
Production Requirement
          |
          v
      BARE_PCB_BOARD
          |
          v
JUSDA CORPORATIONS PVT LTD
          |
          v
  Scheduling Agreement
          |
          v
     Schedule Lines
          |
          v
Delivery Dates + Quantities
          |
          v
    Supplier Delivery
          |
          v
     Goods Receipt

This provides better visibility of future procurement requirements.

Schedule Lines

Schedule lines are a key component of the Scheduling Agreement.

They define when the material is required and how much material is required.

A Scheduling Agreement can contain multiple schedule lines.

For example:

Scheduling Agreement
        |
        +-- Schedule Line 1
        |       |
        |       +-- Delivery Date : 10.01.2026
        |       +-- Quantity      : 1,000 EA
        |
        +-- Schedule Line 2
        |       |
        |       +-- Delivery Date : 20.01.2026
        |       +-- Quantity      : 1,500 EA
        |
        +-- Schedule Line 3
                |
                +-- Delivery Date : 30.01.2026
                +-- Quantity      : 2,000 EA

This allows the organization to communicate future requirements to the supplier.

The supplier can use the planned delivery schedule to prepare material and organize logistics.

The purchasing team can also monitor whether deliveries are occurring according to the planned schedule.

Scheduling Agreement Delivery Flow

The Scheduling Agreement process can be represented as:

Scheduling Agreement
        |
        v
Schedule Lines
        |
        v
Planned Delivery Dates
        |
        v
Planned Quantities
        |
        v
Supplier Delivery
        |
        v
Goods Receipt
        |
        v
Inventory Update
        |
        v
MMBE Verification

The Scheduling Agreement therefore connects procurement planning with supplier delivery and inventory availability.

This is especially important in manufacturing environments where material availability directly affects production continuity.

Contract Agreement vs Scheduling Agreement

Contract Agreements and Scheduling Agreements are both Purchasing Agreements, but their business purposes are different.

A Contract Agreement focuses primarily on establishing a long-term purchasing commitment.

A Scheduling Agreement focuses primarily on recurring deliveries according to planned dates and quantities.

Feature	Contract Agreement	Scheduling Agreement
Main Purpose	Long-term purchasing commitment	Planned recurring deliveries
Quantity Contract	Yes	No
Value Contract	Yes	No
Primary Control	Quantity or Value	Delivery Date and Quantity
Schedule Lines	Not the primary focus	Core component
Procurement Focus	Long-term commitment	Delivery planning
Example Supplier	UMECO	JUSDA CORPORATIONS PVT LTD
Example Material	SMT Wipe Roll	BARE_PCB_BOARD

The overall concept is:

Contract Agreement
        |
        v
Long-Term Purchasing Commitment
        |
        +------------------+
        |                  |
        v                  v
Quantity Control       Value Control

Whereas:

Scheduling Agreement
        |
        v
Long-Term Procurement Arrangement
        |
        v
Schedule Lines
        |
        v
Delivery Date + Quantity
Overall Purchasing Agreement Process

The complete Purchasing Agreement process used in this project is:

                    Purchasing Agreements
                             |
              +--------------+--------------+
              |                             |
              v                             v
      Contract Agreement           Scheduling Agreement
              |                             |
        +-----+-----+                       |
        |           |                       v
        v           v                 Schedule Lines
    Quantity      Value                     |
    Contract     Contract                   v
        |           |                 Delivery Planning
        |           |                       |
        +-----+-----+                       |
              |                             |
              +--------------+--------------+
                             |
                             v
                    Procurement Execution
                             |
                             v
                       Goods Receipt
                             |
                             v
                    Inventory Management
                             |
                             v
                     MMBE Verification
                             |
                             v
                    Invoice Verification
                             |
                             v
                     Final Validation
SAP MM Transactions

The Purchasing Agreement process uses the relevant SAP S/4HANA MM transactions.

Contract Agreements
Transaction	Purpose
ME31K	Create Contract
ME32K	Change Contract
ME33K	Display Contract
Scheduling Agreements
Transaction	Purpose
ME31L	Create Scheduling Agreement
ME32L	Change Scheduling Agreement
ME33L	Display Scheduling Agreement
ME38	Maintain Scheduling Agreement Schedule Lines
Procurement Execution
Transaction	Purpose
ME21N	Create Purchase Order
Goods Receipt
Transaction	Purpose
MIGO	Goods Receipt
Inventory Verification
Transaction	Purpose
MMBE	Stock Overview
Invoice Verification
Transaction	Purpose
MIRO	Invoice Verification
SAP Transaction Flow
Purchasing Agreement
        |
        v
Procurement Execution
        |
        v
      MIGO
        |
        v
      MMBE
        |
        v
      MIRO
End-to-End Procurement Flow

The Purchasing Agreement is not an isolated SAP document.

It is connected with the overall procurement lifecycle.

The end-to-end business process is:

Business Requirement
        |
        v
Supplier Selection
        |
        v
Material Requirement
        |
        v
Purchasing Agreement
        |
        v
Procurement Execution
        |
        v
Goods Receipt
        |
        v
Inventory Update
        |
        v
Stock Verification
        |
        v
Invoice Verification
        |
        v
Financial Processing
        |
        v
Final Validation