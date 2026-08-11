# Consignment Procurement Testing

## Objective

The purpose of testing is to verify that the complete Consignment Procurement process functions correctly from consignment purchasing through goods receipt, supplier-owned stock verification, ownership transfer, final unrestricted-use stock verification and vendor settlement.

---

# Test Scenario

The following business scenario was executed successfully.

| Test Case | Transaction | Status |
|-----------|------------|--------|
| Consignment Purchasing Information Record Created | PIR | ✅ Passed |
| Consignment Purchase Order Created | ME21N | ✅ Passed |
| Consignment Goods Receipt Posted | MIGO – 101 | ✅ Passed |
| Supplier Consignment Stock Verified | MMBE | ✅ Passed |
| Consignment Stock Availability Confirmed | MMBE | ✅ Passed |
| Consignment Stock Transferred to Own Stock | MIGO – 411 K | ✅ Passed |
| Company-Owned Unrestricted Stock Verified | MMBE | ✅ Passed |
| Consignment Withdrawal Identified | MRKO | ✅ Passed |
| Unsettled Consignment Withdrawal Verified | MRKO | ✅ Passed |
| Vendor Settlement and Settlement Document Created | MRKO | ✅ Passed |

---

# Test Results

The following validations were performed during testing.

- The Consignment Purchasing Information Record was successfully created and verified for supplier `7000010015 – JUSDA CORPORATIONS PVT LTD` and material `BARE_PCB_BOARD`.

- The Consignment Purchase Order `4500002176` was successfully created with item category `K – Consignment`, quantity `500 EA`, plant `CN01` and storage location `CS01`.

- Goods Receipt was successfully posted in MIGO using Movement Type `101` for `500 EA` of `BARE_PCB_BOARD` against Purchase Order `4500002176`.

- MMBE successfully confirmed that the received material was available as supplier-owned consignment stock at plant `CN01` and storage location `CS01`.

- The consignment stock was successfully verified as physically available at the company location while ownership remained with the supplier before the ownership transfer.

- Movement Type `411 K` was successfully posted in MIGO to transfer `500 EA` from supplier-owned consignment stock to company-owned stock.

- Final MMBE verification successfully confirmed that the transferred `500 EA` was available under **Unrestricted Use**, indicating company ownership.

- The corresponding consignment withdrawal was successfully identified in MRKO for the supplier `JUSDA CORPORATIONS PVT LTD`.

- The `500 EA` withdrawal with a settlement amount of `250,000.00 INR` was successfully identified as an unsettled consignment transaction in MRKO.

- Vendor settlement was successfully executed in MRKO and settlement document `1105` was created for the consignment withdrawal.

---

# Conclusion

The Consignment Procurement process was tested successfully without any errors.

All major activities including Consignment Purchasing Information Record creation, Consignment Purchase Order creation, Goods Receipt, supplier-owned consignment stock verification, `411 K` ownership transfer, final unrestricted-use stock verification and MRKO vendor settlement worked as expected.

The complete Consignment Procurement process was successfully validated from procurement through inventory ownership transfer and final vendor settlement.