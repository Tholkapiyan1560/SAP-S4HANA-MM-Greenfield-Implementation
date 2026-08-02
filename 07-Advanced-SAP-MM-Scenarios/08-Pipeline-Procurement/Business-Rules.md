# Pipeline Procurement Business Rules

## Overview

Pipeline Procurement is used for materials that are supplied continuously through a pipeline and are consumed directly without creating Goods Receipts.

Typical examples include:

- Industrial Gas
- Water
- Steam
- Electricity
- Compressed Air

---

# Business Rules

## Rule 1

Pipeline materials do not require Goods Receipt (GR).

---

## Rule 2

Consumption is recorded directly using Goods Issue (MIGO).

---

## Rule 3

Pipeline materials are procured through a Pipeline Info Record.

---

## Rule 4

The vendor supplies the material continuously through a physical pipeline.

---

## Rule 5

Settlement is performed periodically using transaction **MRKO**.

---

## Rule 6

Settlement quantity is calculated based on the actual consumed quantity.

---

## Rule 7

Pipeline material valuation is determined from the price maintained in the Pipeline Info Record.

---

## Rule 8

A Cost Center is mandatory when consuming pipeline material using movement type **201**.

---

## Rule 9

Pipeline withdrawals remain available for settlement until MRKO is executed.

---

## Rule 10

Once settlement is completed, the pipeline withdrawal documents are marked as settled and cannot be settled again.

---

# Benefits

- Eliminates repetitive Goods Receipt postings.
- Simplifies procurement of continuously supplied materials.
- Supports automatic settlement based on actual consumption.
- Reduces manual inventory transactions.
- Improves procurement efficiency for utilities and industrial gases.