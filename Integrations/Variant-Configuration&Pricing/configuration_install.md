
for AVC installation please consider chapter 7.8 of the installation guide:
* https://help.sap.com/doc/6b11678926d3409bbfea8897cb34d10f/2023/en-US/INST_OP2023.pdf
  
Find also more details in attached consulting note:
0002987015 - Manual installation of VCH AFL for S/4 HANA Advanced Variant Configuration S/4 Release 1909OP and following

For AVC you have to download the relevant AFL version from the SAP Software Download Center:
* https://launchpad.support.sap.com/#/softwarecenter/template/products/_APP=00200682500000001943&_EVENT=NEXT&HEADER=Y&FUNCTIONBAR=Y&EVENT=TREE&NE=NAVIGATE&ENR=73554900100800000266&V=MAINT&TA=ACTUAL/SAP%20S4HANA

Consider also the note 0001898497 for AFL versioning.
You can check the AFL installation with report VCH_HL_AFL_CHECK.

For more details please contact your local SAP consultant.

AVC is the new configuration application and stands for "Advanced Variant Configuration".

The backend system has to be S4CORE, ECC doesn't support AVC.
In ECC you can use only the classic Variant Configuration, supported by component LO-VC.
Within AVC there are several FIORI apps, e.g. Advanced Variant Configuration (app ID F2460), Simulate Configuration Models (app ID F2570) or VC Modeling Environment (app ID PMEVC).
You can find more details of the apps in the SAP FIORI library:
* https://fioriappslibrary.hana.ondemand.com/sap/fix/externalViewer/#

In case of any problems and errors in this apps the support component starts with LO-VCH. You can find the supporting component in the app description in the FIORI library under implementation information - support.
