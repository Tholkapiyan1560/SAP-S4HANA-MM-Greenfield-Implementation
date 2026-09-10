# 01 | Activate and Configure Split Valuation

## 1. Overview

This document demonstrates the initial configuration of **Split Valuation** in SAP S/4HANA MM for Plant `CN01`.

The scenario is designed for Novatech Electronics Pvt. Ltd. to manage the **same material under separate valuation types** based on the procurement source.

### Configuration Scope

1. Check Split Valuation status
2. Activate Split Material Valuation using `OMW0`
3. Verify the activation
4. Open Valuation Category configuration using `OMWC`
5. Create custom Valuation Category `N`
6. Verify the created Valuation Category
7. Create External Valuation Type `NT-EX`
8. Create Internal Valuation Type `NT-IN`
9. Allocate the Valuation Category to Plant `CN01`
10. Verify the final Split Valuation configuration

### Business Scenario

| Field | Value |
|---|---|
| Company | Novatech Electronics Pvt. Ltd. |
| Plant | `CN01` |
| Valuation Category | `N` |
| Description | `NOVA VAL CAT` |
| Internal Valuation Type | `NT-IN` |
| External Valuation Type | `NT-EX` |
| Purpose | Separate valuation of internal and external stock |

### Configuration Flow

```text
OMW0
   ↓
Activate Split Material Valuation
   ↓
OMWC
   ↓
Create Valuation Category
N - NOVA VAL CAT
   ↓
Create Valuation Types
   ├── NT-IN → Internal / In-house
   └── NT-EX → External Procurement
   ↓
Allocate to Plant CN01
   ↓
Split Valuation Ready
```

---

# 2. Check Split Valuation Status – OMW0

The Split Valuation configuration is initiated using transaction `OMW0`.

### Transaction Code

```text
OMW0
```

The **Activate Valuation** screen contains two options:

- Split material valuation active
- Split material valuation not active

Initially, the system shows:

**Split material valuation not active**

### Screenshot – Initial OMW0 Status

![OMW0 Initial Screen](<../../assets/Split-Valuation/01-Configuration/OMW0-Initial-Screen.png>)

The screenshot provides the initial configuration evidence before Split Material Valuation is activated.

---

# 3. Activate Split Material Valuation

In transaction `OMW0`, select:

**Split material valuation active**

Save the configuration.

SAP displays the confirmation message:

**Your entry has been saved**

### Screenshot – Split Valuation Activated

![OMW0 Split Valuation Activated](<../../assets/Split-Valuation/01-Configuration/OMW0-Split-Valuation-Activated.png>)

The selected option confirms that Split Material Valuation has been activated successfully.

### Result

```text
Split Material Valuation
          ↓
        ACTIVE
```

---

# 4. Open Valuation Category Configuration – OMWC

After activating Split Valuation, the valuation category configuration is maintained using transaction `OMWC`.

### Transaction Code

```text
OMWC
```

The **Plant CN01: Allocate Valuation Categories** screen is displayed.

This screen is used to allocate valuation categories to the plant and maintain the related valuation types.

### Screenshot – OMWC Plant CN01

![OMWC Plant CN01 Valuation Categories](<../../assets/Split-Valuation/01-Configuration/Split-Valuation-Configuration-Complete.png>)

The screenshot shows Plant `CN01` and the valuation category allocation area.

---

# 5. Create Custom Valuation Category – N

For the Novatech Electronics scenario, a custom valuation category is created.

### Valuation Category Details

| Field | Value |
|---|---|
| Valuation Category | `N` |
| Description Category | `NOVA VAL CAT` |
| Default External Procurement | `NT-EX` |
| Default In-house Procurement | `NT-IN` |

The valuation category acts as the parent configuration for the internal and external valuation types.

### Screenshot – Valuation Category Creation

![Valuation Category Creation](<../../assets/Split-Valuation/01-Configuration/Valuation-Category-Creation.png>)

The screenshot shows the creation of valuation category `N` with the description `NOVA VAL CAT`.

The procurement defaults are maintained as:

```text
External Procurement → NT-EX
In-house Procurement  → NT-IN
```

---

# 6. Save and Verify Valuation Category

After entering the required values, the valuation category is saved.

SAP confirms that valuation category `N` has been created.

### Screenshot – Valuation Category Created

![Valuation Category Created](<../../assets/Split-Valuation/01-Configuration/Valuation-Category-Created.png>)

The screenshot provides evidence that the custom valuation category was successfully created.

### Created Configuration

```text
Valuation Category : N
Description        : NOVA VAL CAT
External Type      : NT-EX
Internal Type      : NT-IN
```

---

# 7. Create External Valuation Type – NT-EX

The external valuation type is created for stock obtained through **external procurement**.

### Valuation Type

```text
NT-EX
```

### Configuration Details

| Field | Value |
|---|---|
| Valuation Type | `NT-EX` |
| External Purchase Orders | `2` |
| Internal Purchase Orders | `2` |
| Account Category Reference | `0001` |
| Reference | Reference for raw materials |

### Screenshot – External Valuation Type Creation

![External Valuation Type Creation](<../../assets/Split-Valuation/01-Configuration/Valuation-type-EX-Creation.png>)

The screenshot shows valuation type `NT-EX` being created with account category reference `0001`.

After saving, SAP confirms the creation.

### Screenshot – External Valuation Type Created

![External Valuation Type Created](<../../assets/Split-Valuation/01-Configuration/Valuation-type-EX-Created.png>)

The screenshot confirms:

**Valuation Type NT-EX was/were created**

### Result

```text
NT-EX
  ↓
External Procurement Stock
```

---

# 8. Create Internal Valuation Type – NT-IN

The internal valuation type is created for the **internal / in-house stock scenario**.

### Valuation Type

```text
NT-IN
```

### Configuration Details

| Field | Value |
|---|---|
| Valuation Type | `NT-IN` |
| External Purchase Orders | `0` |
| Internal Purchase Orders | `2` |
| Account Category Reference | `0001` |
| Reference | Reference for raw materials |

### Screenshot – Internal Valuation Type Creation

![Internal Valuation Type Creation](<../../assets/Split-Valuation/01-Configuration/Valuation-type-IN-Creation.png>)

The screenshot shows the creation of valuation type `NT-IN`.

The configuration contains:

```text
External Purchase Orders → 0
Internal Purchase Orders → 2
Account Category Reference → 0001
```

After saving, SAP confirms the creation.

### Screenshot – Internal Valuation Type Created

![Internal Valuation Type Created](<../../assets/Split-Valuation/01-Configuration/Valuation-type-IN-Created.png>)

The screenshot confirms:

**Valuation Type NT-IN was/were created**

### Result

```text
NT-IN
  ↓
Internal / In-house Stock
```

---

# 9. Allocate Valuation Category to Plant CN01

The custom valuation category `N` is allocated to Plant `CN01`.

The completed configuration contains:

| Field | Value |
|---|---|
| Plant | `CN01` |
| Valuation Category | `N` |
| Description | `NOVA VAL CAT` |
| External Valuation Type | `NT-EX` |
| Internal Valuation Type | `NT-IN` |
| Status | Active |

### Screenshot – Plant CN01 Allocation

![CN01 Valuation Category Allocation](<../../assets/Split-Valuation/01-Configuration/Split-Valuation-Configuration-Complete.png>)

The screenshot shows the valuation category `N` allocated to Plant `CN01`, with `NT-EX` and `NT-IN` maintained as the corresponding valuation types.

The SAP status message confirms:

**Valtn Category CN01 N was/were activated**

### Result

```text
Plant CN01
    ↓
Valuation Category N
    ↓
 ┌───────────────┐
 │               │
 ▼               ▼
NT-IN           NT-EX
Internal        External
```

---

# 10. Final Split Valuation Configuration

The final configuration provides separate valuation types under the same valuation category.

```text
                    Plant CN01
                        │
                        ▼
              Valuation Category N
                 NOVA VAL CAT
                        │
              ┌─────────┴─────────┐
              ▼                   ▼
            NT-IN               NT-EX
          Internal             External
          Valuation            Valuation
              │                   │
              ▼                   ▼
       Internal Stock       External Stock
```

### Final Configuration

| Configuration | Value |
|---|---|
| Split Material Valuation | Active |
| Plant | `CN01` |
| Valuation Category | `N` |
| Description | `NOVA VAL CAT` |
| Internal Valuation Type | `NT-IN` |
| External Valuation Type | `NT-EX` |

### Screenshot – Final Configuration

![Final Split Valuation Configuration](<../../assets/Split-Valuation/01-Configuration/Split-Valuation-Configuration-Complete.png>)

This screenshot provides the final evidence that the valuation category is active for Plant `CN01` and the required valuation types are configured.

---

# 11. Configuration Summary

| Step | Activity | Transaction / Configuration | Status |
|---:|---|---|---|
| 1 | Check Split Valuation | `OMW0` | Completed |
| 2 | Activate Split Valuation | `OMW0` | Completed |
| 3 | Open Valuation Category Configuration | `OMWC` | Completed |
| 4 | Create Valuation Category | `N` | Created |
| 5 | Create External Valuation Type | `NT-EX` | Created |
| 6 | Create Internal Valuation Type | `NT-IN` | Created |
| 7 | Allocate Category to Plant | `CN01` | Completed |
| 8 | Verify Final Configuration | `OMWC` | Completed |

---

# 12. Business Scenario

The purpose of this configuration is to allow Novatech Electronics to manage the same material separately depending on how the stock is sourced.

For example:

```text
Same Material
      │
      ▼
Copper Wire
      │
      ├── NT-IN
      │     ↓
      │   Internal / In-house Stock
      │
      └── NT-EX
            ↓
          External Procurement Stock
```

The two stocks can subsequently be handled independently during procurement and inventory transactions.

---

# 13. How This Configuration Will Be Used

The configuration created in this document will be used in the following project scenarios:

### Internal Scenario

```text
Material
   ↓
NT-IN
   ↓
Manual Initial Stock
   ↓
Stock Transfer
   ↓
Internal Stock
```

### External Scenario

```text
Material
   ↓
NT-EX
   ↓
PR
   ↓
PO
   ↓
MIGO
   ↓
MIRO
   ↓
External Stock
```

### Final Analysis

```text
                 Same Material
                       │
             ┌─────────┴─────────┐
             ▼                   ▼
           NT-IN               NT-EX
        Internal Stock      External Stock
             │                   │
             └─────────┬─────────┘
                       ▼
                     MMBE
                       │
                       ▼
           Separate Stock & Value
```

---

# 14. SAP Transactions Used

| Transaction | Purpose |
|---|---|
| `OMW0` | Activate Split Material Valuation |
| `OMWC` | Maintain and allocate Valuation Categories |

---

# 15. Complete Process Summary

```text
                 OMW0
                  │
                  ▼
        Check Initial Status
                  │
                  ▼
      Activate Split Valuation
                  │
                  ▼
                 OMWC
                  │
                  ▼
       Create Valuation Category
          N - NOVA VAL CAT
                  │
          ┌───────┴───────┐
          ▼               ▼
        NT-IN           NT-EX
       Internal         External
          │               │
          └───────┬───────┘
                  ▼
              Plant CN01
                  │
                  ▼
       Configuration Complete
                  │
                  ▼
      Material Master Configuration
                  │
                  ▼
       Internal / External Scenarios
                  │
                  ▼
                 MMBE
```

---

# 16. Final Outcome

```text
✓ Split Material Valuation Activated
✓ Valuation Category N Created
✓ NOVA VAL CAT Configured
✓ NT-IN Internal Valuation Type Created
✓ NT-EX External Valuation Type Created
✓ Valuation Category Allocated to Plant CN01
✓ Configuration Successfully Completed
✓ Ready for Material Master Configuration
```



