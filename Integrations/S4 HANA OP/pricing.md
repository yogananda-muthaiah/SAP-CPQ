
* [Pricing Conditions - Help Documentation](https://help.sap.com/docs/SAP_S4HANA_ON-PREMISE/7b24a64d9d0941bda1afa753263d9e39/5e49b753128eb44ce10000000a174cb4.html)

|Purpose                             |Transaction Code|Description                                                      |
|------------------------------------|----------------|-----------------------------------------------------------------|
|Display Pricing Procedure (SD)      |V/08            |Define/Display Pricing Procedures (Sales & Distribution)         |
|Display Pricing Procedure (MM)      |OMWK            |Define/Display Calculation Schemas (Materials Management)        |
|Display Condition Types             |V/06            |Define/Display Condition Types (SD)                              |
|                                    |M/06            |Define/Display Condition Types (MM)                              |
|Display Access Sequence             |V/07            |Define/Display Access Sequences (SD)                             |
|                                    |M/07            |Define/Display Access Sequences (MM)                             |
|Display Condition Tables            |V/03            |Define/Display Condition Tables (SD)                             |
|                                    |M/03            |Define/Display Condition Tables (MM)                             |
|Maintain Condition Records (SD)     |VK11, VK12, VK13|Create, Change, Display Condition Records (Price, Discount, etc.)|
|Maintain Condition Records (MM)     |MEK1, MEK2, MEK3|Create, Change, Display Purchasing Condition Records             |
|Display Pricing Analysis (Sales Doc)|Pricing Analysis|In sales order: Menu ‚Üí Item ‚Üí Conditions ‚Üí Analysis        |
|Pricing Report                      |V/LD            |Pricing Report for Sales                                         |
|Condition Maintenance (General)     |VV11, VV12, VV13|Output Condition Records                                         |



#### To analyze the pricing procedure determination process in SAP S/4HANA SD, the primary transaction code is OVKK. This transaction allows you to view and configure how the system determines which pricing procedure is applied to a sales document, based on the combination of Sales Organization, Distribution Channel, Division, Customer Pricing Procedure, and Document Pricing Procedure.

### Key T-codes for Pricing Procedure Determination Analysis:

* OVKK: Maintain/Display Pricing Procedure Determination (core T-code for analyzing the determination logic).
* VOV8: Display/Change Sales Document Types (to check which Document Pricing Procedure is assigned to a sales document type).
* XD02 / VD02: Change Customer Master (to check which Customer Pricing Procedure is assigned to a customer in the Sales Area data).
* OVKP: Customer Pricing Procedure maintenance.
* OVKI: Document Pricing Procedure maintenance.

### Usage Example:

* Use OVKK to display the determination table and see which pricing procedure is assigned for a given combination.
* Use VOV8 to check what Document Pricing Procedure is set for a specific sales document type.
* Use XD02/VD02 to verify the Customer Pricing Procedure in the customer master record.
* These T-codes provide a full overview of how the system selects the pricing procedure for each transaction, allowing you to analyze and troubleshoot pricing determination in detail.

### Related
* Are T-codes like OVKK and V/08 used specifically for pricing procedure determination
* Can I use T-code VK11 to analyze condition records involved in pricing
* Which transaction codes help define and assign access sequences in SAP SD
* Is OVKP the main T-code for creating or copying customer-specific pricing procedures
* How do T-codes VOV8 and OVKJ relate to sales document and billing pricing procedures
