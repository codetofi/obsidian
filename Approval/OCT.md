1) Issue description:  
2) Reporter Name:  
3) Impacted Table:  
4) Account Name:  
5) Analysis:  
-  
6) Impacted records:  
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:
    

1) Issue description:  INC2024092501820: DaaS Production Issue ACT - To update correct ship date in ECC/OVP, as Ship date showing future date : 09/05/2024
2) Reporter Name:  ytan7
3) Impacted Table:  alm_asset
4) Account Name:  ACT WoG
5) Analysis:  
-  OVP has initially sent us the wrong shipment date 09/20/2024.
- Now it is corrected in OVP and we need to update the correct shipment date in SNOW 09/05/2024
6) Impacted records:  150
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:    DaaS | System Issue | OVP-Data Issues
12) Solution Steps:
    - Update the correct shipment date  09/05/2024 in SNOW



1) Issue description:  INC2024093001159: DaaS Production Issue The task state flipped to "Pending for billing " but One Hard Time Request.
2) Reporter Name:  nkamaruddin
3) Impacted Table: sc_task
4) Account Name:  Valvoline
5) Analysis:  
-  The asset is created in delivered state and hence Valvoline - Shipment and POD API BR got triggered.
- Due to this the task was moved to pending for billing.
6) Impacted records:  3
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  
12) Solution Steps:
        -  Move the task to closed complete state.

INC2024100101059
INC2024100101166
INC2024100101181
INC2024100101784
INC2024100101697
INC2024100200029
INC2024100200355


INC2024100101181
analysis:
Cmn location table does not have any record so it cannot fetch the values.
All records from this account do not have SSC order number

Analysis:  

SSC Return Order Number after clicking execute return button.

- Upon validation, the following error occurred:

{
	"code":"400",
	"data":"",
	"description":"head shipToId is missing;  head extShipToWarehouse or ShipToWarehouse is missing; ",
	"errorCode":"E004",
	"success":false
}


- As per the system logic the "shipToId" ,"extShipToWarehouse"  are getting fetched from  Locations (cmn_location) table from the u_location_code field.

- Since there is no record for this account in Location table we are getting this error.

- @**COT Team**, Please check on this.
  
INC2024100101784
acceptance state is empty thats y in use didnt trigger

INC2024100200362
Akbar has similar ticket
Script inc - SSCCreateInboundDeliveryOrder - 347 CMN location does not have location code

Analysis:  

SSC Return Order Number after clicking execute return button.

- Upon validation, the following error occurred:

 {
	"code":"400",
	"data":"",
	"description":"head shipFrId is null, but cannot null; inboundDoAddr article 1 bpId is null, but cannot null; ",
	"errorCode":"E002",
	"success":false
}


- As per the system logic the "shipFrId" ,"bpId"  are getting fetched from  Locations (cmn_location) table from the u_location_code field.

- Since it is empty we are receiving this error
  ![[Pasted image 20241003001740.png]]
- @**COT Team**, Please update this field with the appropriate value to resolve the error, after which the reporter can retrigger/reprocess  execute return the for the impacted record.


INC2024100200355. Approval la in use trigger panniruka bro ippo task state close aaganu varudhu.


INC2024100200029 - doubt
Return order is not raised, that's the reason it aligned with new inventory delivery date.
Asset is not processed by SSC yet and there is no update in lenovo SNOW.

Please check with SSC to process the order. 

INC2024100101697 -We need to rename the asset as DND since we cancel the order and the asset are back to lenovo WH. MSCT 


1) Issue description:  INC2024100200362 DaaS Production Issue MYOB: SCTASK0522181 is not generating SSC Return Order Number after clicking execute return button.
2) Reporter Name:  sdaud1
3) Impacted Table:  sc_task
4) Account Name:  MYOB
5) Analysis:  
-  - Upon validation, the following error occurred:
 {
"code":"400",
"data":"",
"description":"head shipFrId is null, but cannot null; inboundDoAddr article 1 bpId is null, but cannot null; ",
"errorCode":"E002",
"success":false
}
- As per the system logic the "shipFrId" ,"bpId" are getting fetched from Locations (cmn_location) table from the u_location_code field.
- Since it is empty we are receiving this error
6) Impacted records:  1
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:


INC2024100400666 - u_customer_stockroom_warehouse is empty that's the reason we are getting this error.


Findings:  We've identified that the location records data was manipulated, as this table is not audited.

SNOW IT raised a HI ticket (**CS7670738**) to identify the reason behind this data manipulation.

Temporary Solution: COT needs to update the data (Account, Location Type, Ship to, Active, Location code, SSC warehouse) on the location record.

Impacted Location record: https://lenovoau.service-now.com/now/nav/ui/classic/params/target/cmn_location_list.do%3Fsysparm_query%3Dsys_idSTARTSWITHe1841271db569d50c6b253dbd39619c6%26sysparm_first_row%3D1%26sysparm_view%3D


**@itsupport** please have this ticket assigned to COT to execute the temporary solution.

Hi @sdaud1 ,
Analysis:  
SSC Return Order Number after clicking execute return button.

- Upon validation, the following error occurred:
 {

"code":"400",

"data":"",

"description":"head shipFrId is null, but cannot null; inboundDoAddr article 1 bpId is null, but cannot null; ",

"errorCode":"E002",

"success":false

}
- As per the system logic the "shipFrId" ,"bpId" are getting fetched from Locations (cmn_location) table from the u_location_code field.

- Since it is empty we are receiving this error
  
  Location record to be updated:
  https://lenovoau.service-now.com/cmn_location.do?sys_id=e1841271db569d50c6b253dbd39619c6&sysparm_record_target=cmn_location&sysparm_record_row=1&sysparm_record_rows=1&sysparm_record_list=sys_idSTARTSWITHe1841271db569d50c6b253dbd39619c6%5EORDERBYDESCsys_updated_on

- @COT Team, Please update this field with the appropriate value to resolve the error, after which the reporter can retrigger/reprocess execute return the for the impacted record.
@itsupport Kindly transfer this ticket to the COT team.

1) Issue description:  INC2024100101784 -the return order was cancelled per client request, we need to move the asset back to IN USE in service now and SSC.
2) Reporter Name:  mcorbalan
3) Impacted Table:  alm_asset
4) Account Name:  Fairstone
5) Analysis:  
-  Initially we transfered this ticket to MSCT team.
- Ahmid's comment:
  Hi SNOW IT, as per latest sharing by SNOW IT on Oct 03, these fields need to be updated in SNOW without using third party asset upload. But as checked, MSCT is not having access to update any field in the asset table/asset level. Would need SNOW IT to assist for this ticket
6) Impacted records:  1
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:




INC2024100900891 - reqorderutil - 686



1) Issue description:  INC2024101000383 DaaS Production Issue Please assist to turn off the “Notification” setting in ServiceNow for Martin D Bendig
2) Reporter Name:  easare
3) Impacted Table:  
4) Account Name:  
5) Analysis:  
-  
6) Impacted records:  
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:


the reason the post order button was not present is because the deal type for the partner determination record is indirect hence the partner details did not populated because of which the  post order button was not visible

below is the screenshot

![[Pasted image 20241014163230.png]]

COT team please check whether the empty value in fulfillment method of the contract 6900008609 is correct and the deal type for the partner determination record is valid or not 

https://lenovoau.service-now.com/u_partner_determination_list.do?sysparm_query=u_account.nameLIKECisco%20Systems%20Internetworking%20Iletisim%20Hizmetleri%20Limited%20Sirketi%5Eu_countrySTARTSWITHTR&sysparm_first_row=1&sysparm_view=


INC2024101401421 - the contract fulfillment method is empty that's y in the br it's enterning the else.
Inside the else the we are checking for dealtype is Empty
So we should validate both is the fulfillment method being  empty is right and if it's right then deal type for the partner determination record is valid or not 



1) Issue description:  INC2024101401421: DaaS Production Issue Lenovo Turkey order REQ0174263 - SCTASK0525332 Post to ACSL Issue
2) Reporter Name:  mimran6
3) Impacted Table:  sc_task
4) Account Name:  cisco
5) Analysis:  
-  In the task post order button was supposed to be visible instead post RR was present and it was clicked by the reporter.
- Partner Order Number is generated
- The reason the post order button was not present is because the deal type for the partner determination record is indirect hence the partner details did not populated because of which the  post order button was not visible.
6) Impacted records:  
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:
- SMO need to cancel the partner order number and the related ECC number(ECC is empty in SNOW)
- SNOW IT should re trigger the br or update u_post_order, u_partner_name and u_partner_id field to make the Post order button visible.


INC2024101301419 - assets are not having the model thats y porduct model list is empty so receiving "In order to 'Start Billing', the task needs to have at least one asset. Please check the 'RR Order Details' tab and verify that an asset is linked to this task." -- this message.
The contract does not have any Main Serialised i tem configured. -- we are getting this info message coz hardware model has no u_mainserializeditem in "Y"


"u_contractnumber=6900008951 "^u_higheritemnumber=1 "^u_productcategoryINHW,3PHW^NQu_contractnumber=" + gr.request_item.cat_item.model.u_contractnumber + "^u_higheritemnumber=" + gr.request_item.cat_item.model.u_primarylinenumber + "^u_productcategoryINCOI,POI^u_mainserializeditem=Y"

1) Issue description: SNOW e client informed that they are not seeing the SN,. TN information of below orders. We need to resend the info to their system. 
2) Reporter Name: Mariana Corbalan.
3) Impacted Table: Asset.
4) Account Name: Valvoline.
5) Analysis: 
1) For 1asset record1, the Shipped status has been updated after 4 hours from the creation of the assets and  the shipment API is not triggered due to this issue. 
2) Need to trigger the shipment  
6) Impacted records: 1 asset record.
7) Additional info required from the reporter: N/A.
8) Proposed temporary solution: Same as Solution steps
9) Permanent Solution: Already escalated and Business need to check with OWB team for the RCA. 
10) Cause of the issue (RCA): System issue - OVP - Data issues
11) Solution Steps: 
Need to trigger the Shipment 



INC2024102201838

PF34EM9S
PF365EEY
C02G535FMD6R
C02G5546ML85
PF31NDBE
LKVPXFM221

PF34EM9S - SCTASK0528138 - account dose not have any location yet.

PF365EEY - SCTASK0528067 - Didn't have location when execute return was clicked.

C02G535FMD6R - SCTASK0528066 -  Didn't have location when execute return was clicked.

C02G5546ML85 - SCTASK0528063  - Didn't have location when execute return was clicked.

PF31NDBE - SCTASK0528043 - Didn't have location when execute return was clicked.

LKVPXFM221 - SCTASK0527912-  SerialNo LKVPXFM221 is not exist - check with SSC


For the below 4 assets the location record for the account in the cmn_location table didn't exist that's the reason for the error we received from SSC. Now the location records have been created, kindly re-process.
PF31NDBE
C02G5546ML85
C02G535FMD6R
PF365EEY


For this PF34EM9S asset, the cmn_location table does not have any location record for the asset's account that's the reason we are receiving the error.
@COT team kindly check on this.


For this LKVPXFM221 assest we are receiving the error from SSC:
{
	"code":"400",
	"data":"",
	"description":"SerialNo LKVPXFM221 is not exist;",
	"errorCode":"E002",
	"success":false
}
SSC to check the reason for the error message sent.


1) Issue description:  INC2024102200373 DaaS Production Issue AU-PwC AU- Remove Original Shipment Date on devices
2) Reporter Name:  lyap2
3) Impacted Table:  alm_asset
4) Account Name:  
5) Analysis:  
-  Reporter wants SNOW IT to remove the shipment date as the assets have arrived at the CFS.
- Once the return order task is attached the previous shipment date is removed but when the Ship POD API field is changed to shipped, the shipment date is updated with the current date.
- In order to solve any confusions that could arise due to this, we are requested to remove the shipment date.
6) Impacted records:  25
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:
- Remove the shipment date for the provided assets



INC2024102202831

Upon analysis it is found that,
For the 68 SN under the SCTASK0519819 the acceptance status is empty because the shipment and POD api has not been executed. This because the OVP has sent us the shipped status and shipment date after the asset creation.

For SN MWRP4WL9HC shipment and POD api has been executed but there's still time for the asset to get deemed accepted.

For SN PF4XNCSQ we'll take this for internal approval to execute the shipment and POD api.



1) Issue description:  DaaS Production Issue Please check why these orders acceptance are empty and to please update the installed date in the asset table
2) Reporter Name:  anhoaf
3) Impacted Table:  alm_asset
4) Account Name:  cisco
5) Analysis:  
-  Upon analysis it is found that,
	For the 68 SN under the SCTASK0519819 the acceptance status is empty because the shipment and POD api has not been executed. This because the OVP has sent us the shipped status and shipment date after the asset creation.
-  For SN PF4XNCSQ it is whole unit replacement so shipment and POD didn't get triggered we'll have to do manually as previously aligned
6) Impacted records:  69
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:
- Need to re-tirgger the shipment and POD api for the assets


Hi OVP team,

We have an ITSM INC2024102202831 DaaS Production Issue Please check why these orders acceptance are empty and to please update the installed date in the asset table.

OVP has sent us the shipped status and shipment date after the asset creation.

Kindly provide us the RCA for sending us the shipped status and shipment date after the asset creation. This would help us to proceed with the execution of Shipment and POD api as a temporary work around. 

Hi Xinghao,

Good day!

We’ve noticed an issue where the shipped status for assets is being received after their creation, rather than being updated at the time the assets are created.

Could you please investigate this and let us know the reason for the delay?

Looking forward to your response.

Note: This issue has happened for 68 assets.
![[Pasted image 20241029153859.png]]



|          |
| -------- |
| PF539HPQ |
| PF53LAZG |
| PF539FGB |
| PF53LB00 |
| PF53L479 |
| PF53LAZ5 |
|          |
| PF539FF2 |
| PF53LD9Q |
| PF53FLMM |
| PF539FHH |
| PF53L8NM |
| PF53L6F6 |
|          |
| PF539FGR |
| PF53L8PG |
| PF53LAXS |
| PF53L1WT |
| PF53L8RV |
| PF53L6HZ |
| PF53L46D |
| PF53L6HF |
| PF53L8SB |
| PF53L6DC |
| PF53L1Y0 |
| PF53L6FK |
| PF53LAYR |
| PF53L1YE |
| PF53LAY6 |
| PF53L8Q0 |
| PF53FNV5 |
| PF53KZPS |
| PF539FJL |
| PF53L485 |
| PF53LB0E |
| PF53L8QK |
| PF53LB16 |
| PF53FLMT |
| PF539HQ0 |
| PF53FLLD |
| PF53FNT9 |
| PF53L1XA |
| PF53L6EA |
| PF53KZQK |
| PF53LB0S |
| PF53L470 |
| PF53L1WD |
| PF539FFX |
| PF53L45Z |
| PF539FFF |
| PF53KZQ4 |
| PF53L6EQ |
| PF53L6GH |
| PF53FNTJ |
| PF53KZQY |
| PF539FH5 |
| PF539FHZ |
| PF53LB1M |
| PF53L6DT |
| PF53L8NZ |
| PF53L6G2 |
| PF53L454 |
| PF53FNSX |
| PF53L1YV |
| PF53L6H0 |
| PF53L1ZJ |
| PF53LB22 |
| PF53L45F |
| PF53L8RA |
| PF53L8QY |
1) Issue description:  DaaS Production Issue Please assist to check why this task SCTASK0521566 tranche ID was updated in asset level but missing in task level (Oct tranche)
2) Reporter Name:  anhoaf
3) Impacted Table:  sc_task
4) Account Name:  cisco
5) Analysis:  
-  Upon analysis we found that the SCTASK0521566 has been manually moved to close complete from open. The script that populates the tranche ID requires the task to be in pending for billing state.
-  Now CSC has reopned the task and they want us to Re open the RITM and REQ
6) Impacted records:  1
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:
    -  Re-open the RITM and REQ


INC2024102302361 - REQ0157063 PF3V4HS8
INC2024102402831 -  REQ0173544 PF3ZPYJY
INC2024102202134 - PC2AG1WA



1) Issue description:  DAAS service now the return order was cancelled per client request. Then we need to change the status of the asset back to "in use".  
2) Reporter Name:  mcorbalan
3) Impacted Table:  alm_asset
4) Account Name:  Fairstone
5) Analysis:  
-  The return order was cancelled per client request
- SSC had updated the status to In Use in SSC and MSCT had reverted the Shipment/Delivery date and status to In use
- Snow IT to update the acceptance status for the assets
6) Impacted records:  2
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:
- Snow IT to update the acceptance status for the assets
Approved :
https://lenovoau.service-now.com/now/nav/ui/classic/params/target/alm_asset_list.do%3Fsysparm_query%3Dserial_numberINPF3ZPYJY%2CPF3V4HS8%26sysparm_first_row%3D1%26sysparm_view%3D



