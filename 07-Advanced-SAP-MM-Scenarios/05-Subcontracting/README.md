# Subcontracting

## Overview

Subcontracting in SAP S/4HANA Materials Management (MM) is a procurement process in which a company provides required components or materials to an external supplier for processing or assembly, and the supplier returns the completed or processed material.

In this project, the subcontracting scenario is designed around a realistic electronics manufacturing model for **Novatech Electronics Pvt. Ltd.**

Novatech performs the initial **MLB / PCB manufacturing** internally, while certain projects require the remaining manufacturing activities to be performed by an external subcontractor.

The subcontractor performs activities such as:

- Mechanical assembly
- Functional testing
- Programming / configuration
- Final assembly
- Other agreed processing activities

The completed product is then returned to Novatech and received into inventory through SAP.

---

## Business Scenario

Novatech Electronics Pvt. Ltd. manufactures electronic products and operates an internal manufacturing facility for **MLB / PCB production**.

For certain projects, Novatech does not perform the complete manufacturing cycle internally. Instead, the PCB / MLB stage is completed at the Novatech plant, while the remaining assembly and processing activities are outsourced to an approved subcontractor.

For this project, the subcontracted product is:

**`SMART_CONTROL_BOARD`**

The finished material is assembled by an external subcontractor using components provided by Novatech.

### Manufacturing Scenario

```text
                    NOVATECH
                       │
                       ▼
              PCB / MLB Manufacturing
                       │
                       ▼
              Semi-Finished Material
                       │
                       │
             Components Provided
                       │
                       ▼
             External Subcontractor
                       │
          ┌────────────┼────────────┐
          │            │            │
          ▼            ▼            ▼
      Assembly      Testing     Programming
          │            │            │
          └────────────┼────────────┘
                       │
                       ▼
              Completed Product
                       │
                       ▼
                   NOVATECH
                       │
                       ▼
              Finished Goods Stock