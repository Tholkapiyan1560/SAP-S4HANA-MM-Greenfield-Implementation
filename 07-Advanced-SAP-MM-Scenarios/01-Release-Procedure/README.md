# 05 | Releasing Procedure

## 📌 Introduction

The **Release Procedure** in SAP S/4HANA Materials Management (MM) is used to control and approve purchasing documents before they can proceed to the next stage of the procurement process.

In a real business environment, purchase requisitions and purchase orders may require approval from different levels of management depending on factors such as:

- Purchase value
- Material or service
- Purchasing organization
- Plant
- Purchasing group
- Document type
- Business approval hierarchy

The release procedure ensures that purchasing documents are reviewed and approved by the appropriate authorized users before they are processed further.

---

# 🎯 Business Scenario

For the **Novatech Electronics Pvt. Ltd.** SAP S/4HANA implementation project, a structured approval process is configured for purchasing documents.

The project demonstrates both:

```text
Purchase Requisition (PR) Release
            ↓
Purchase Order (PO) Release
```

The purpose is to simulate a real-world procurement approval hierarchy where purchasing documents require authorization before further processing.

---

# 🏢 Project Context

### Company

**Novatech Electronics Pvt. Ltd.**

### Procurement Process

```text
Purchase Requirement
        ↓
Purchase Requisition
        ↓
PR Approval / Release
        ↓
Purchase Order
        ↓
PO Approval / Release
        ↓
Further Procurement Processing
```

The release procedure introduces an approval control between document creation and subsequent procurement activities.

---

# 🔐 Release Procedure Concept

The release procedure determines **who must approve a purchasing document and in what sequence**.

A simplified approval structure used in this project is:

```text
                Purchasing Document
                        │
                        ▼
                 Release Strategy
                        │
             ┌──────────┴──────────┐
             ▼                     ▼
        PR Release              PO Release
             │                     │
             ▼                     ▼
       Approval Levels        Approval Levels
             │                     │
             ▼                     ▼
       Final Approval         Final Approval
```

SAP determines the applicable release strategy based on the configured release conditions.

---

# 📚 Release Procedure Types Covered

This project focuses on the **Release Procedure with Classification** approach.

The implementation is demonstrated separately for:

### 1. Purchase Requisition Release

```text
PR Creation
    ↓
Release Strategy Determination
    ↓
Approval
    ↓
PR Released
```

### 2. Purchase Order Release

```text
PO Creation
    ↓
Release Strategy Determination
    ↓
Engineer Approval
    ↓
Senior Engineer Approval
    ↓
Manager Approval
    ↓
PO Fully Released
```

---

# 📝 Purchase Requisition Release

The PR release procedure demonstrates how a purchase requisition can be placed under an approval strategy based on configured release conditions.

The project covers:

```text
Release Procedure Configuration
        ↓
Release Strategy
        ↓
PR Creation
        ↓
Release Status Verification
        ↓
PR Release
        ↓
Final PR Approval
```

### PR Approval Concept

A release strategy can determine whether the PR requires approval before it can be converted into a subsequent purchasing document.

The detailed configuration and testing are documented in:

- `01-PR-Release-Procedure-Creation.md`
- `02-PR-Release.md`

---

# 📦 Purchase Order Release

The PO release procedure demonstrates a **three-level approval hierarchy**.

The scenario uses:

| Level | Release Code | Role |
|---|---|---|
| 1 | `EN` | Engineer |
| 2 | `SR` | Senior Engineer |
| 3 | `MA` | Manager |

The approval sequence is:

```text
Engineer
   ↓
Senior Engineer
   ↓
Manager
   ↓
Final Release
```

---

# 🏷️ PO Release Strategy Demonstrated

The PO scenario uses:

```text
Release Group     : $N – PO REL GRP
Release Strategy  : 03 – MANAGER STRATEGY
```

The release codes are:

```text
EN → ENGINEER
SR → SENIOR ENGINEER
MA → MANAGER
```

The PO initially has:

```text
Release Indicator: N – NOT APPROVED
```

After all required approvals:

```text
Release Indicator: A – APPROVED SUCCESSFULLY
```

---

# 🔄 PO Release Flow Demonstrated

The complete PO testing performed in this project is:

```text
ME21N
Create Purchase Order
        ↓
PO 4500002281
        ↓
Release Strategy Determined
        ↓
N – NOT APPROVED
        ↓
EN – Engineer Release
        ↓
SR – Senior Engineer Release
        ↓
MA – Manager Release
        ↓
A – APPROVED SUCCESSFULLY
        ↓
PO Fully Released
```

---

# 🧪 PO Release Test Scenario

The PO used for the demonstration contains:

| Field | Value |
|---|---|
| PO Number | `4500002281` |
| Supplier | `7000005028` |
| Supplier Name | UMECO TRADERS |
| Material | `FINGER-COTS` |
| Quantity | 20 PC |
| Net Price | ₹5 / PC |
| PO Type | Standard PO |
| Release Group | `$N` |
| Release Strategy | `03` |
| Engineer Release Code | `EN` |
| Senior Engineer Release Code | `SR` |
| Manager Release Code | `MA` |

---

# 🖥️ SAP Transactions Used

| T-Code | Purpose |
|---|---|
| `CT04` | Create/maintain characteristics |
| `CL01` | Create class |
| `CL02` | Change/display class |
| `ME51N` | Create Purchase Requisition |
| `ME52N` | Change Purchase Requisition |
| `ME53N` | Display Purchase Requisition |
| `ME54N` | Individual PR Release |
| `ME55` | Collective PR Release |
| `ME21N` | Create Purchase Order |
| `ME22N` | Change Purchase Order |
| `ME23N` | Display Purchase Order |
| `ME29N` | Individual PO Release |
| `ME28` | Collective PO Release |

---

# 🔑 Important Release Procedure Elements

A release procedure consists of several important configuration elements.

### Release Group

Groups related release strategies together.

Example:

```text
$N – PO REL GRP
```

### Release Strategy

Defines the approval strategy that should be applied.

Example:

```text
03 – MANAGER STRATEGY
```

### Release Code

Identifies an approval level or responsible role.

Example:

```text
EN – Engineer
SR – Senior Engineer
MA – Manager
```

### Release Indicator

Shows the current approval status of the purchasing document.

Example:

```text
N – NOT APPROVED
A – APPROVED SUCCESSFULLY
```

---

# 📊 Approval Status Concept

The PO release status changes progressively as each approval is completed.

### Initial

```text
EN → Required
SR → Waiting
MA → Waiting

Indicator → N – NOT APPROVED
```

### After Engineer

```text
EN → ✓
SR → Required
MA → Waiting
```

### After Senior Engineer

```text
EN → ✓
SR → ✓
MA → Required
```

### After Manager

```text
EN → ✓
SR → ✓
MA → ✓

Indicator → A – APPROVED SUCCESSFULLY
```

This demonstrates the sequential nature of the configured approval process.

---

# 🎯 Objectives of This Scenario

The release procedure implementation is intended to demonstrate practical understanding of:

- SAP MM purchasing document approvals
- Release groups
- Release strategies
- Release codes
- Release indicators
- Classification-based release procedures
- PR approval process
- PO approval process
- Sequential approval hierarchy
- Individual document release
- Final release status verification

---

# 📁 Project Structure

```text
05-Releasing-Procedure/
│
├── README.md
│
├── 01-PR-Release-Procedure-Creation.md
│
├── 02-PR-Release.md
│
├── 03-PO-Release-Procedure-Creation.md
│
└── 04-PO-Release.md
```

---

# 📖 Documentation Map

### `01-PR-Release-Procedure-Creation.md`

Documents the configuration and setup of the **Purchase Requisition Release Procedure**.

### `02-PR-Release.md`

Documents the actual **PR creation, release, approval status, and testing**.

### `03-PO-Release-Procedure-Creation.md`

Documents the configuration and setup of the **Purchase Order Release Procedure**.

### `04-PO-Release.md`

Documents the complete **PO release execution**, including:

```text
PO Creation
    ↓
Release Strategy
    ↓
Engineer Release
    ↓
Senior Engineer Release
    ↓
Manager Release
    ↓
Final Approval
```

---

# 💼 Business Benefits

A properly configured release procedure provides:

- **Approval Control** – Purchasing documents are approved by authorized personnel.
- **Segregation of Duties** – Different approval levels can be assigned to different roles.
- **Procurement Governance** – Purchasing decisions follow an organizational hierarchy.
- **Risk Reduction** – Unauthorized purchasing commitments can be controlled.
- **Transparency** – The current approval status is visible within SAP.
- **Auditability** – The release history provides evidence of the approval process.
- **Standardization** – The same approval rules can be applied consistently.

---

# 🧠 Key Learning

The most important concept demonstrated in this scenario is that **document creation and document approval are separate steps**.

For example:

```text
PO Created
    ≠
PO Fully Released
```

A PO can initially be created with:

```text
N – NOT APPROVED
```

and then move through multiple release levels:

```text
EN
 ↓
SR
 ↓
MA
```

until it reaches:

```text
A – APPROVED SUCCESSFULLY
```

Only after completing the required release sequence does the PO reach its final approved state.

---

# 🚀 Scenario Outcome

The **Releasing Procedure** scenario successfully demonstrates how SAP S/4HANA MM can control purchasing documents through structured approval workflows.

### PR

```text
PR Creation
     ↓
Release Strategy
     ↓
Approval
     ↓
PR Released
```

### PO

```text
PO Creation
     ↓
Strategy 03
     ↓
Engineer – EN
     ↓
Senior Engineer – SR
     ↓
Manager – MA
     ↓
Approved Successfully
```

This scenario adds an important **procurement governance and approval-control process** to the Novatech Electronics SAP S/4HANA MM implementation project.