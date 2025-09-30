* KOBEV is used for adding requirements related to header conditions.
* KOBED is used for adding requirements related to both header and item conditions.
* FRM_KONDI_WERT - It is a formula routine used for alternative condition value calculation.


* Whenever a coding is done or a formula is written you do it by using FORMS. The purpose of encapsulating the code under a FORM is because we should have an option to call the same Form in the some other requirement. So instead of writing the program all over again we justcall the Form with its name.
* KOBED_002 and KOBEV_002 are just the name given under which the Formula is written.
* Being a Functional consultant we do not have to worry about the coding part but these FORMand ENDFORM contains the relevant formulaes for the specific business requirement.
* In the above case FORM KOBED_002 the formula written under it means that system would first check whether the item category attached for an item in that condition item number in SO is relevant for pricing or not.
* Do not bother about FORM KOBEV_002 as it does not holdany meaning particularly for this program.


##### The names KOBEV and KOBED are SAP standard naming conventions:

* KOBEV = Konditionen Objekt Bewertung – Vorkondition (Precondition check)
* KOBED = Konditionen Objekt Bewertung – Detail (Detailed check)
* The suffix (e.g., _931) corresponds to the routine number you define in VOFM. So KOBED_931 and KOBEV_931 are the header and item routines for requirement number 931



#### Value	Meaning
0	Success – The operation was successful.
1	Failure or Not Found – Often means a condition was not met or no match was found.
2	Invalid Input or Error – Could indicate incorrect parameters or data issues.
3	Authorization Error – Sometimes used to indicate lack of permissions.
4	Other Errors – Depends on the context; could be a system or logic error.


### In the context of pricing routines:

* SY-SUBRC = 0 → Condition is valid and should be included in pricing.
* SY-SUBRC ≠ 0 → Condition is not valid and should be excluded.



#### KOBEV_XXX – Header-Level Requirement Check

* Used to determine if a pricing condition should be considered based on header data only (structure KOMK).
* Improves performance by skipping item-level checks when not needed.


#### KOBED_XXX – Item-Level Requirement Check

* Used to validate pricing conditions using both header (KOMK) and item (KOMP) data.
* Called only if KOBEV returns SY-SUBRC = 0.


#### FRM_KONDI_WERT_XXX – Alternative Condition Value Calculation

* Used when you want to override the standard condition value calculation logic.
* Implemented via a formula routine assigned in the pricing procedure (field CalTy).
* Allows custom logic for calculating condition values (e.g., discounts, surcharges).



### Tax Calculation is not Supported

tax determination via the TTE (Tax Transaction Engine) is not supported. Simple, condition-based tax calculation like MWST is possible. However, multiple tax levels, tax exemption licenses (for example for Italy, Brazil and France) or tax calculation via external tax engine like Vertex are not supported. 
