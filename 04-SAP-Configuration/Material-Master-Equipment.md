# Equipment Material Master

## Overview

This document describes the creation of the Equipment Material Master for an **AOI (Automated Optical Inspection) Machine** in SAP S/4HANA Materials Management (MM). The material master contains all procurement, inventory, storage, and accounting information required for equipment procurement and inventory management.

---

# Transaction Code

**MM01 – Create Material**

---

# Material Details

| Field | Value |
|------|------|
| Material Code | V23.AOI EQP |
| Material Description | AOI Machine (Automated Optical Inspection) |
| Material Type | ROH – Raw Material |
| Material Group | EQP |
| Base Unit of Measure | EA |
| Plant | CN01 |
| Storage Location | EQ01 |
| Purchasing Group | EQP |
| Storage Bin | EQP-01-01 |
| Storage Condition | 01 |
| Temperature Condition | 02 |
| Gross Weight | 500 KG |
| Net Weight | 450 KG |
| Volume | 2 m³ |
| Dimensions | 1800 × 1200 × 1800 mm |
| Price Control | V (Moving Average Price) |
| Standard Price | ₹150,000 |
| Goods Receipt Processing Time | 2 Days |

---

# Step 1 – Material Creation Initial Screen & View Selection

The material creation process begins by entering the material number, selecting the material type, and choosing the required material master views.

### Screenshot

![Material Creation Initial Screen & View Selection](../assets/Material%20Master/EQUIPMENT/Material-Creation-Initial-Screen-View-Selection.png)

---

# Step 2 – Organizational Levels

The organizational levels define where the material will be managed within the enterprise.

| Organizational Level | Value |
|----------------------|-------|
| Plant | CN01 |
| Storage Location | EQ01 |

### Screenshot

![Organizational Levels](../assets/Material%20Master/EQUIPMENT/Organizational-Levels.png)

---

# Step 3 – Basic Data

The Basic Data view stores the general characteristics of the equipment.

### Information Maintained

- Material Description
- Material Group
- Base Unit of Measure
- Gross Weight
- Net Weight
- Volume
- Equipment Dimensions

### Screenshot

![Basic Data](../assets/Material%20Master/EQUIPMENT/Basic-Data.png)

---

# Step 4 – Purchasing Data

The Purchasing view contains procurement-related information used during the purchasing process.

### Information Maintained

- Purchasing Group
- Material Group
- Order Unit
- Goods Receipt Processing Time

### Screenshot

![Purchasing Data](../assets/Material%20Master/EQUIPMENT/Purchasing-Data.png)

---

# Step 5 – Plant & Storage Data

The Plant Storage Data view contains inventory and warehouse management information.

### Information Maintained

- Plant
- Storage Location
- Storage Bin
- Storage Condition
- Temperature Condition

### Screenshot

![Plant Storage Data](../assets/Material%20Master/EQUIPMENT/Plant-Storage-Data.png)

---

# Step 6 – Accounting Data

The Accounting view contains the valuation and financial information for the equipment material.

### Information Maintained

| Field | Value |
|------|------|
| Valuation Class | 3000 |
| Price Control | V (Moving Average Price) |
| Standard Price | ₹150,000 |
| Currency | INR |

### Screenshot

![Accounting Data](../assets/Material%20Master/EQUIPMENT/Accounting-Data.png)

---

# Step 7 – Material Created Successfully

After maintaining all mandatory views and validating the master data, the Equipment Material Master was successfully created in SAP S/4HANA.

### Screenshot

![Material Created Successfully](../assets/Material%20Master/EQUIPMENT/Material-Created-Successfully.png)

---

# Material Master Summary

| Configuration | Status |
|--------------|--------|
| Material Creation | ✅ Completed |
| Organizational Levels | ✅ Completed |
| Basic Data | ✅ Completed |
| Purchasing Data | ✅ Completed |
| Plant & Storage Data | ✅ Completed |
| Accounting Data | ✅ Completed |
| Material Master Created | ✅ Completed |

---

# Business Benefits

- Centralizes equipment master data.
- Supports procurement and inventory management.
- Enables Purchase Requisition creation.
- Supports Purchase Order processing.
- Enables Goods Receipt and Inventory Management.
- Supports Invoice Verification.
- Integrates inventory valuation with Financial Accounting.

---

# Conclusion

The Equipment Material Master for the **AOI Machine** was successfully created in SAP S/4HANA MM. All procurement, inventory, storage, and accounting information has been maintained, enabling the material to participate in the complete Procure-to-Pay (P2P) process.

---

# Document Information

| Item | Details |
|------|---------|
| Module | SAP S/4HANA Materials Management (MM) |
| Business Process | Material Master |
| Transaction Code | MM01 |
| Project | SAP S/4HANA MM Greenfield Implementation |
| Document Type | Master Data Documentation |
| Status | ✅ Completed |