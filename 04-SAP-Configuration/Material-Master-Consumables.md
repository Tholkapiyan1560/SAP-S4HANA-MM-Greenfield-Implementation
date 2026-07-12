# Material Master - Consumables

## Overview

The Material Master contains all the information required to procure, store, value, and consume materials within SAP S/4HANA. In this Greenfield Implementation project, the consumable material **SMT WIPER ROLL** was created for use in SMT production processes.

---

# Business Requirement

SMT Wiper Rolls are consumable materials used during PCB assembly for cleaning SMT machine nozzles and boards. These materials are procured from vendors and managed through inventory until consumption.

---

# Material Details

| Field | Value |
|------|------|
| Material | SMT.WIPER ROLL |
| Material Type | ROH (Raw Material) |
| Industry Sector | Electronics Factory |
| Plant | CN01 |
| Storage Location | CS01 |
| Material Group | CONS |
| Base Unit | PC |
| Purchasing Group | CS0 |
| Valuation Class | 3000 |
| Price Control | V |
| Moving Price | 120 INR |

---

# Step 1 - Material Creation Initial Screen

The material creation process begins by entering the material number, selecting the industry sector, and choosing the material type.

### Screenshot

![Material Creation Initial Screen](../assets/Material%20Master/CONSUMABLES/Material-Creation-Initial-Screen.png)

---

# Step 2 - View Selection

The required material master views were selected for procurement, inventory management, and accounting.

Selected Views:

- Basic Data 1
- Basic Data 2
- Purchasing
- Plant Data / Storage 1
- Plant Data / Storage 2
- Accounting 1

### Screenshot

![View Selection](../assets/Material%20Master/CONSUMABLES/View-Selection.png)

---

# Step 3 - Organizational Levels

The material was extended to the required organizational levels.

| Organizational Level | Value |
|---------------------|-------|
| Plant | CN01 |
| Storage Location | CS01 |

### Screenshot

![Organizational Levels](../assets/Material%20Master/CONSUMABLES/Organizational-Levels.png)

---

# Step 4 - Basic Data

The general material information including description, material group, dimensions, and base unit of measure was maintained.

### Screenshot

![Basic Data](../assets/Material%20Master/CONSUMABLES/Basic-Data.png)

---

# Step 5 - Purchasing Data

Purchasing-related information such as Purchasing Group and procurement settings were maintained.

### Screenshot

![Purchasing Data](../assets/Material%20Master/CONSUMABLES/Purchasing-Data.png)

---

# Step 6 - Plant & Storage Data

Plant-specific information including storage bin, storage conditions, and inventory management data was maintained.

### Screenshot

![Plant Storage Data](../assets/Material%20Master/CONSUMABLES/Plant-Storage-Data.png)

---

# Step 7 - Accounting Data

Accounting information including valuation class, price control, currency, and moving average price was maintained.

### Screenshot

![Accounting Data](../assets/Material%20Master/CONSUMABLES/Accounting-Data.png)

---

# Step 8 - Material Created Successfully

The material master record was successfully created and saved in SAP S/4HANA.

### Screenshot

![Material Created Successfully](../assets/Material%20Master/CONSUMABLES/Material-Created-Successfully.png)

---

# Configuration Summary

| Configuration | Value |
|--------------|-------|
| Material | SMT.WIPER ROLL |
| Material Type | ROH |
| Material Group | CONS |
| Plant | CN01 |
| Storage Location | CS01 |
| Purchasing Group | CS0 |
| Valuation Class | 3000 |
| Price Control | Moving Average Price (V) |
| Moving Price | 120 INR |
| Status | ✅ Successfully Created |

---

# Conclusion

The consumable material **SMT WIPER ROLL** was successfully configured in SAP S/4HANA with all mandatory organizational, purchasing, plant, storage, and accounting views. This material is now available for procurement, inventory management, and consumption within the manufacturing process.