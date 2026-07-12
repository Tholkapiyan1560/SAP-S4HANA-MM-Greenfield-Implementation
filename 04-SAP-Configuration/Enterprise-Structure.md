# Enterprise Structure

## Overview

The Enterprise Structure defines the organizational hierarchy for the SAP S/4HANA Greenfield Implementation. It establishes the organizational units required for procurement, inventory management, and purchasing operations within NovaTech Electronics Manufacturing Pvt. Ltd.

---

## 1. Company

The Company represents the highest organizational unit used for consolidated financial reporting.

### Configuration

| Field | Value |
|------|------|
| Company | NT01 |
| Description | NovaTech Electronics Manufacturing Pvt. Ltd. |

### Screenshot

![Company](../assets/Enterprise%20Structure/Company-Creation.png)

---

## 2. Company Code

The Company Code is the legal entity where procurement and inventory transactions are recorded.

### Configuration

| Field | Value |
|------|------|
| Company Code | NT0100 |
| Description | NovaTech Electronics Manufacturing Pvt. Ltd. |

### Screenshot

![Company Code](../assets/Enterprise%20Structure/Company-Code.png)

---

## 3. Plant

The manufacturing plant is located at Sriperumbudur and is responsible for iPhone MLB and FATP production.

### Configuration

| Field | Value |
|------|------|
| Plant | CN01 |
| Description | NovaTech Manufacturing Plant |

### Screenshot

![Plant](../assets/Enterprise%20Structure/Plant.png)

---

## 4. Storage Locations

Storage locations are maintained to manage inventory based on material categories.

### Configuration

| Storage Location | Description |
|-----------------|-------------|
| CN01CS01 | Consumables Store |
| CN01FX01 | Fixtures Store |
| CN01EQ01 | Equipment Store |

### Screenshot

![Storage Locations](../assets/Enterprise%20Structure/Storage-Locations.png)

---

## 5. Purchasing Organization

The Purchasing Organization manages procurement activities across the manufacturing plant.

### Configuration

| Field | Value |
|------|------|
| Purchasing Organization | POR1 |
| Description | Central Procurement Organization |

### Screenshot

![Purchasing Organization](../assets/Enterprise%20Structure/Purchasing-Organization.png)

---

## 6. Purchasing Groups

Purchasing Groups are responsible for procurement activities based on material categories.

### Configuration

| Purchasing Group | Description |
|-----------------|-------------|
| CON | Consumables Procurement |
| PRD | Production Procurement (Fixtures) |
| EQP | Equipment Procurement |

### Screenshot

![Purchasing Groups](../assets/Enterprise%20Structure/Purchasing-Groups.png)

---

## 7. Enterprise Assignments

The organizational units were assigned to establish the SAP enterprise structure.

### Company → Company Code

![Company Assignment](../assets/Enterprise%20Structure/Assignment-Company-Code.png)

---

### Company Code → Plant

![Plant Assignment](../assets/Enterprise%20Structure/Assignment-Plant.png)

---

### Purchasing Organization → Company Code

![Purchasing Organization to Company Code](../assets/Enterprise%20Structure/Assignment-POrg-Company.png)

---

### Purchasing Organization → Plant

![Purchasing Organization to Plant](../assets/Enterprise%20Structure/Assignment-POrg-Plant.png)

---

### Enterprise Structure Overview

![Enterprise Structure Overview](../assets/Enterprise%20Structure/Organization-Overview.png)

---

## Configuration Summary

| Configuration | Status |
|--------------|--------|
| Company | ✅ Completed |
| Company Code | ✅ Completed |
| Plant | ✅ Completed |
| Storage Locations | ✅ Completed |
| Purchasing Organization | ✅ Completed |
| Purchasing Groups | ✅ Completed |
| Enterprise Assignments | ✅ Completed |

---

## Business Outcome

The Enterprise Structure has been successfully configured to support procurement and inventory management processes for an electronics manufacturing environment. This structure provides the organizational foundation required for Material Management (SAP MM) activities, including master data creation, procurement execution, inventory control, and Procure-to-Pay (P2P) processes.