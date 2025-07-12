
You can see some information about this topic in attached KBA 3599036  
3599036 - Warnings when pricing extensions have not been implemented for the user exits in the pricing procedure


See in point 2 of the solution in the KBA ( Regarding standard user exits)
"Not all the standard pricing user exits available in the ERP/S4 backend are supported in “Variant Configuration and Pricing” . 

#### For a list of supported standard formulas visit page
* https://help.sap.com/docs/variant-configuration-and-pricing/supported-standard-pricing-exits/supported-standard-pricing-exits

 

#### Documentation for supported pricing requirements
https://help.sap.com/docs/variant-configuration-and-pricing/supported-standard-pricing-exits/pricing-requirements
> If any Requirements like 21 and 23 are not in the list


#### Regarding supported condition value formulas
* https://help.sap.com/docs/variant-configuration-and-pricing/supported-standard-pricing-exits/condition-value-formulas
> Condition value formula 48 is not in the list.

The possible options that you have to remove the warnings about missing formulas are:

  1)  Use setting “Ignore Non-Implemented Extensions” mentioned in the KBA 3599036 
  but this will work only in Development and Test systems, not in production

 
  2) You can create your own implementations of the formulas.
##### See in the Extension Guide documentation
* https://help.sap.com/docs/variant-configuration-and-pricing/extension-guide-for-sap-variant-configuration-and-pricing/extensions
