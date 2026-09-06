# 02 | PR Release Procedure

## 1. Overview

This document demonstrates the complete **Purchase Requisition (PR) Release Procedure** in SAP S/4HANA MM.

The process covers:

1. Creating a Purchase Requisition
2. Saving the Purchase Requisition
3. Verifying the assigned Release Strategy
4. Opening the PR in `ME54N`
5. Performing Engineer approval
6. Performing Senior Engineer approval
7. Performing Manager approval
8. Verifying the final release status
9. Displaying the final released PR

### Business Scenario

| Field | Value |
|---|---|
| Company | Novatech Electronics Pvt. Ltd. |
| Process | Standard Consumable Procurement |
| Material | `SMT.WIPE ROLL-MESH` |
| Quantity | 10 PC |
| Plant | NOVA TECH PV... |
| Purchasing Group | CS0 |
| Delivery Date | 30.09.2026 |
| PR Number | `10001752` |

### Release Strategy

The PR follows a three-level approval procedure:

```text
Purchase Requisition
        │
        ▼
Engineer Approval
Release Code: EN
        │
        ▼
Senior Engineer Approval
Release Code: SR
        │
        ▼
Manager Approval
Release Code: MA
        │
        ▼
Final Approval
```

---

# 2. Create Purchase Requisition

The Purchase Requisition is created using transaction `ME51N`.

### Transaction Code

```text
ME51N
```

The following procurement details are entered:

| Field | Value |
|---|---|
| Document Type | NB – Purchase Requisition |
| Material | SMT.WIPE ROLL-MESH |
| Quantity | 10 PC |
| Plant | NOVA TECH PV... |
| Purchasing Group | CS0 |
| Delivery Date | 30.09.2026 |
| Storage Location | Consumable... |

### Screenshot – ME51N PR Creation

![ME51N PR Creation](<../../assets/Release-procedure/PR-Release/ME51N-PR-Creation.png>)

---

# 3. Save the Purchase Requisition

After entering the required PR details, the Purchase Requisition is saved.

SAP generates the following PR number:

```text
PR Number: 10001752
```

The SAP status message confirms successful creation of the Purchase Requisition.

### Screenshot – PR Created

![PR Created](<../../assets/Release-procedure/PR-Release/PR-Created.png>)

---

# 4. Verify the PR Release Strategy

After creation, the PR is checked to verify the Release Strategy assigned by SAP.

The **Release Strategy** tab displays the approval hierarchy.

### Release Strategy Details

| Field | Value |
|---|---|
| Release Group | `PR REL GRP` |
| Release Strategy | `03 – MANAGER STATERGY` |
| Release Indicator | `N – NOT APPROVED` |

The approval hierarchy contains:

```text
EN → ENGINEER
SR → SENIOR ENGINEER
MA → MANAGER
```

### Screenshot – Initial Release Strategy

![Initial PR Release Strategy](<../../assets/Release-procedure/PR-Release/ME54N-Initial-Release.png>)

The screenshot shows the PR before completion of the approval process, with the release strategy assigned and the first approval level pending.

---

# 5. Open PR in ME54N

Individual Purchase Requisition release is performed using transaction `ME54N`.

### Transaction Code

```text
ME54N
```

Enter the Purchase Requisition number:

```text
10001752
```

The release screen displays the configured release strategy and approval levels.

The release procedure is performed sequentially.

---

# 6. Engineer Approval

The first approval level is performed by the **Engineer**.

### Release Code

```text
EN
```

### Description

```text
ENGINEER
```

The Engineer reviews the Purchase Requisition and performs the first release.

After successful release:

```text
EN → Released
SR → Pending
MA → Pending
```

### Screenshot – Engineer Release

![Engineer Release EN](<../../assets/Release-procedure/PR-Release/Engineer-Release-EN.png>)

The SAP status bar confirms:

```text
Release effected with release code EN
```

---

# 7. Senior Engineer Approval

After the Engineer releases the PR, the approval moves to the next level.

The second approval is performed by the **Senior Engineer**.

### Release Code

```text
SR
```

### Description

```text
SENIOR ENGINEER
```

After successful release:

```text
EN → Released
SR → Released
MA → Pending
```

### Screenshot – Senior Engineer Release

![Senior Engineer Release SR](<../../assets/Release-procedure/PR-Release/Senior-Engineer-Release-SR.png>)

The SAP status bar confirms:

```text
Release effected with release code SR
```

---

# 8. Manager Approval

After Engineer and Senior Engineer approval, the PR reaches the final approval level.

The final approval is performed by the **Manager**.

### Release Code

```text
MA
```

### Description

```text
MANAGER
```

After successful release:

```text
EN → Released
SR → Released
MA → Released
```

### Screenshot – Manager Release

![Manager Release MA](<../../assets/Release-procedure/PR-Release/Manager-Release-MA.png>)

The SAP status bar confirms:

```text
Release effected with release code MA
```

---

# 9. Final Release Status

After the Manager completes the final approval, the Purchase Requisition receives the final release status.

### Initial Status

```text
N – NOT APPROVED
```

### Final Status

```text
A – APPROVED SUCCESSFULL
```

All three release codes are successfully completed:

| Release Code | Approver | Status |
|---|---|---|
| EN | Engineer | Released |
| SR | Senior Engineer | Released |
| MA | Manager | Released |

### Screenshot – Final Release Status

![PR Final Release Status](<../../assets/Release-procedure/PR-Release/PR-Final-Release-Status.png>)

The screenshot provides the final evidence that all approval levels have been completed.

---

# 10. Final PR Display

After completing all approvals, the Purchase Requisition can be displayed using transaction `ME53N`.

### Transaction Code

```text
ME53N
```

Enter:

```text
Purchase Requisition: 10001752
```

The final PR display can be used to verify the completed release procedure.

### Screenshot – Final PR Display

![PR Final Display](<../../assets/Release-procedure/PR-Release/PR-Final-Display.png>)

The final display confirms the PR details and completed release status.

---

# 11. Final Saved PR

The completed Purchase Requisition is saved after the release processing.

### Screenshot – Final Saved PR

![PR Final Saved](<../../assets/Release-procedure/PR-Release/PR-Final-Saved.png>)

This screenshot provides additional evidence of the completed PR processing.

---

# 12. Complete PR Release Process

The complete SAP process is:

```text
ME51N
   │
   ▼
Create Purchase Requisition
PR 10001752
   │
   ▼
Release Strategy Determined
Strategy 03 – MANAGER STATERGY
   │
   ▼
ME54N
   │
   ▼
Engineer
Release Code EN
   │
   ▼
Senior Engineer
Release Code SR
   │
   ▼
Manager
Release Code MA
   │
   ▼
Final Release
A – APPROVED SUCCESSFULL
   │
   ▼
ME53N
   │
   ▼
Final PR Verification
```

---

# 13. Release Status Progression

The PR moves through the following approval sequence:

```text
N – NOT APPROVED
        │
        ▼
Engineer Release – EN
        │
        ▼
Senior Engineer Release – SR
        │
        ▼
Manager Release – MA
        │
        ▼
A – APPROVED SUCCESSFULL
```

Each approval level must be completed before the PR can proceed to the next level.

---

# 14. Business Purpose

The PR Release Procedure provides controlled approval of procurement requests before further purchasing activities are performed.

For Novatech Electronics Pvt. Ltd., the approval procedure provides:

- Controlled purchasing authorization
- Multi-level approval
- Defined approval responsibilities
- Prevention of unauthorized procurement
- Approval traceability
- Visibility of PR approval status
- Procurement governance
- Standardized purchasing control

---

# 15. SAP Transactions Used

| Transaction | Purpose |
|---|---|
| `ME51N` | Create Purchase Requisition |
| `ME54N` | Individual PR Release |
| `ME53N` | Display Purchase Requisition |

---

# 16. Key SAP Objects Demonstrated

| Object | Value |
|---|---|
| Purchase Requisition | `10001752` |
| Release Group | `PR REL GRP` |
| Release Strategy | `03 – MANAGER STATERGY` |
| Release Code 1 | `EN – ENGINEER` |
| Release Code 2 | `SR – SENIOR ENGINEER` |
| Release Code 3 | `MA – MANAGER` |
| Initial Release Indicator | `N – NOT APPROVED` |
| Final Release Indicator | `A – APPROVED SUCCESSFULL` |

---

# 17. Result

The Purchase Requisition `10001752` was successfully processed through the configured three-level release procedure.

```text
Engineer
   ✓
   │
Senior Engineer
   ✓
   │
Manager
   ✓
   │
Final PR Approval
   ✓
```

The final release indicator confirms:

```text
A – APPROVED SUCCESSFULL
```

The PR has therefore completed the configured approval process and is ready for further procurement processing.

---

# 18. Screenshot Evidence

The following screenshots document the complete PR Release Procedure:

| No. | Screenshot | File |
|---:|---|---|
| 1 | ME51N PR Creation | `ME51N-PR-Creation.png` |
| 2 | PR Created | `PR-Created.png` |
| 3 | Initial Release Strategy | `ME54N-Initial-Release.png` |
| 4 | Engineer Release | `Engineer-Release-EN.png` |
| 5 | Senior Engineer Release | `Senior-Engineer-Release-SR.png` |
| 6 | Manager Release | `Manager-Release-MA.png` |
| 7 | Final Release Status | `PR-Final-Release-Status.png` |
| 8 | Final PR Display | `PR-Final-Display.png` |
| 9 | Final Saved PR | `PR-Final-Saved.png` |

All screenshots are stored under:

```text
assets/Release-procedure/PR-Release/
```

---

# 19. Process Summary

| Step | Activity | Transaction | Result |
|---:|---|---|---|
| 1 | Create PR | `ME51N` | PR `10001752` created |
| 2 | Verify Release Strategy | `ME54N` | Strategy `03` assigned |
| 3 | Engineer Approval | `ME54N` | Release Code `EN` completed |
| 4 | Senior Engineer Approval | `ME54N` | Release Code `SR` completed |
| 5 | Manager Approval | `ME54N` | Release Code `MA` completed |
| 6 | Final Verification | `ME53N` | PR fully approved |

### Final Outcome

```text
PR 10001752
     │
     ▼
Release Strategy 03
     │
     ├── EN – Engineer ✓
     │
     ├── SR – Senior Engineer ✓
     │
     └── MA – Manager ✓
              │
              ▼
     A – APPROVED SUCCESSFULL
```