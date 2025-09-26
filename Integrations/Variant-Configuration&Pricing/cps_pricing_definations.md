For example: Condition status will be made inactive if there is an error during currency conversion

The reasons for being inactive are:

| inactiveFlag      | Description                                     |
|:------------|:------------------------------------------------|
| `A`         | Condition exclusion item                        |
| `K`         | Inactive due to calculation basis               |
| `M`         | Inactive due to manual entry                    |
| `W`         | The document item is statistical                |
| `X`         | Inactive via formulae or inactive due to error  |
| `Y`         | Inactive because of subsequent price            |
| `Z`         | Invisible                                       |
| ` ` (space) | Condition is active                             |




| Calculation Type | Description                          |
|------------------|--------------------------------------|
| A                | Percentage                           |
| B                | Fixed Amount                         |
| C                | Quantity                             |
| D                | Gross weight                         |
| E                | Net weight                           |
| F                | Volume                               |
| G                | Formula                              |
| H                | Percentage (in hundreds)             |
| I                | Percentage (travel expenses)         |
| L                | Points                               |
| M                | Quantity - monthly price             |
| N                | Quantity - yearly price              |
| O                | Quantity - daily price               |
| P                | Quantity - weekly price              |
| Q                | Commodity price                      |
| U                | Percentage FIN                       |
| W                | Percentage (with 6 decimal places)   |




| SubtotalFlag | Description                                         |
|------|-----------------------------------------------------|
| " "  | No separate sub-totals                              |
| 1    | Carry over value to KOMP-KZWI1 (subtotal 1)         |
| 2    | Carry over value to KOMP-KZWI2 (subtotal 2)         |
| 3    | Carry over value to KOMP-KZWI3 (subtotal 3)         |
| 4    | Carry over value to KOMP-KZWI4 (subtotal 4)         |
| 5    | Carry over value to KOMP-KZWI5 (subtotal 5)         |
| 6    | Carry over value to KOMP-KZWI6 (subtotal 6)         |
| 7    | Carry over value to KOMP_BONBA (rebate basis 1)     |
| 8    | Copy values according to KOMP-PREVA (preference value) |
| 9    | Copy values to KOMP-BRTWR (gross value)             |
| A    | Carry over price to KOMP-CMPRE (credit price)       |
| B    | Carry over value to KOMP-WAVWR (cost)               |
| C    | Carry over value to KOMP-GKWRT (statistical value)  |
| D    | Copy value to XWORKD                                |
| E    | Copy value to XWORKE                                |
| F    | Copy value to XWORKF                                |
| G    | Copy value to XWORKG                                |
| H    | Copy value to XWORKH                                |
| I    | Copy value to XWORKI                                |
| J    | Copy value to XWORKJ                                |
| K    | Copy value to XWORKK                                |
| L    | Copy value to XWORKL                                |
| M    | Copy value to XWORKM                                |
| Q    | Reserved (IS-OIL)                                   |
| S    | Copy values to KOMP-EFFWR (effective value)         |
| Y    | Reserved (IS-OIL)                                   |
| Z    | Reserved (IS-OIL)                                   |


| Condition Class | Description                    |
|-----------------|-------------------------------|
| A               | Discount or surcharge          |
| B               | Prices                        |
| C               | Expense reimbursement          |
| D               | Taxes                         |
| E               | Extra pay                     |
| F               | Fees for differential          |
| G               | Tax classification            |
| H               | Determining sales deal         |
| Q               | Totals record for fees only    |
| W               | Wage Withholding Tax           |


| currencyConversionFlag | Description                                                                                   |
|---------------------|-----------------------------------------------------------------------------------------------|
| Rate                | Conversion happens on condition rate before it is multiplied with condition base              |
| Value               | Conversion happens on condition value (after multiplying condition base with condition rate)   |




| Access Date Type | Description                  |
|------------------|-----------------------------|
| KOMK-FBUDA       | Date of services rendered    |
| KOMK-PRSDT       | Price date                   |
| KOMK-FKDAT       | Billing date                 |
| KOMK-ERDAT       | Creation date                |
| KOMK-AUDAT       | Order date                   |




| Datasource | Description                                 |
|------------|---------------------------------------------|
| "" (blank) | Condition technique (old)                   |
| A          | Condition technique (new)                   |
| B          | Cash Flow (FS/Leasing)                      |
| C          | Tax Determination                           |
| D          | Financial mathematics (Leasing)             |
| E          | Cash Discount                               |
| F          | Billing for One-Time Payments               |
| G          | EBP: Price From Product Catalog             |
| H          | Cost                                        |
| I          | Floating Rates / Indexation                 |
| J          | IPM: Basic Value                            |
| K          | EBP: Price From Backend Contract            |
| L          | Social: Requirement Determination           |
| M          | CRM: Condition from ERP Purchasing Contract |
| N          | CRM: Download of an ERP Dispute Case        |
| O          | CRM: Accruals                               |
| Q          | CRM: Pricing                                |
| U          | UBB: Prebilling                             |
| X          | Customer Reserve 1                          |
| Y          | Customer Reserve 2                          |
| Z          | Customer Reserve 3                          |
| EC         | CRM: External Configurator                  |
| CP         | Pricing: Calculation Tool                   |



| manualEntryFlag| Description    
|----------------|----------------------------------|
| " " (space)    | No limitations                   |
| A              | Free                             |
| B              | Automatic entry has priority     |
| C              | Manual entry has priority        |
| D              | Not possible to process manually |


| Zero Value Flag  | Description                                                                                                                        |
|----------------------|------------------------------------------------------------------------------------------------------------------------------------|
| "" (blank) or null   | Conditions are not considered in the condition exclusion logic when their value is zero.<br>Price conditions are deactivated during the price calculation if their rate and value are zero. |
| A                    | Conditions of this type are considered in the exclusion logic even if their value is zero.<br>Condition type with the condition class 'Price' is not deactivated during the price calculation |

| Rounding Rule | Description     |
|---------------|----------------|
| " " (space)   | Commercial     |
| A             | Round up       |
| B             | Round down     |


| Scale Basis         | Description                                 |
|---------------------|---------------------------------------------|
| " " or "" (blank)   | No scales                                   |
| B                   | Value scale                                 |
| C                   | Quantity scale                              |
| D                   | Gross weight scale                          |
| E                   | Net weight scale                            |
| F                   | Volume scale                                |
| G                   | Scale based on a formula                    |
| L                   | Point scale                                 |
| M                   | Time period scale - Month                   |
| N                   | Time period scale - Years                   |
| O                   | Time period scale - Days                    |
| P                   | Time period scale - Week                    |
| R                   | Distance                                    |
| S                   | Number of shipping units                    |


| Scale Order   | Description  |
|---------------|-------------|
| " " (space)   | None        |
| A             | Descending  |
| B             | Ascending   |


| Scale Type   | Description                                      |
|--------------|--------------------------------------------------|
| " " (space)  | can be maintained in condition record            |
| A            | Base-scale                                       |
| B            | To-scale                                         |
| C            | not used                                         |
| D            | Graduated to interval scale                      |


| Structure Flag | Description                |
|----------------|---------------------------|
| A              | Condition to be duplicated |
| B              | Cumulation condition       |


| Access Type   | Description                                                                                   |
|---------------|----------------------------------------------------------------------------------------------|
| " " (space)   | Field in fixed key part                                                                      |
| A             | Field in free key part Hierarchical Access                                                   |
| B             | Key field not relevant for access                                                            |
| C             | Data field from condition table - Not Supported (Note 2030179)                               |
