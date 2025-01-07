1) Issue description:
2) Reporter Name: 
3) Impacted Table:
4) Account Name:   
5) Analysis:   
	- 
7) Impacted records: 
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- 

Hi Shunguo,

Regarding: INC2024120602475: the return order SSC number is not flowing to the order REQ0183555

We are receiving the error from the SSC while processing the return order. 

REQ: REQ0183555
SCTASK: SCTASK0568957
ASSET: PF3ZRT1D

{
	"code":"400",
	"data":"",
	"description":"Order SCTASK0568957 sn PF3ZRT1D is in other open order! ",
	"errorCode":"E003",
	"success":false
}
Kindly advise on this

Thanks,
SNOW IT


1) Issue description: INC2024112700173 investigate invalid PO generated in Task level
2) Reporter Name: sedward1
3) Impacted Table: sc_task
4) Account Name:   Cisco
5) Analysis:   
	- 
7) Impacted records: 
8) Additional info required from the reporter: N/A.
9) Solution steps:


1) Issue description: INC2024120600129: DaaS Production Issue Cisco shipment dates not in payload
2) Reporter Name: joshfi
3) Impacted Table: sc_task
4) Account Name:  Cisco
5) Analysis:   
	- We could see that the cisco shipment api sent us the following error.
	- {"result":{"result":{"obj":{"error":{"message":"Mandatory Parameter is empty","detail":"Param 'ShipmentDate' cannot be empty"},"status":400},"state":"error"}}}
	- Upon checking we could see that the asset has been created first and after 2 hours the shipped status and shipment date has been sent. because of which we have sent the shipment date as empty resulting in the error
1) Impacted records: 8
2) Additional info required from the reporter: N/A.
3) Solution steps:
	- Re-trigger the shipment Api


sedward1 (Guest)

USA000EP579787

17:36 1213066876 by Thoufiq AhamedThoufiq Ahamed17:45

1213066876USA000EP579787 by sedward1 (Guest)sedward1 (Guest)

USA000EP579787

17:45   USA000EP579787 For the Us account PO nu... by Thoufiq AhamedThoufiq Ahamed17:47 |   |
|---|
|USA000EP579787|

For the Us account PO numberCAN000EP577609  - For canada account Po num... by Thoufiq AhamedThoufiq Ahamed17:48

CAN000EP577609  - For canada account Po number

1) All 703 assets don't have the actual del... by Shakeel MohdShakeel MohdEdited

1) All 703 assets don't have the actual delivery dates, Shipment dates. tracking number, carrier name.

2) If SMO don't have the confirmation for Shipment dates and Actual delivery dates  SMO to confirm whether order delivery date (**Only proof because on 2021 there was no logic to update actual delivery dates and shipment dates**)can be updated for all those assets. 

3) If SMO don't have the confirmation Tracking number and carrier name, Please take a confirmation, that it can be updated with Dummy tracking number and carrier name.

[https://lenovoau.service-now.com/alm_asset_list.do?sysparm_tiny=a40NNV76WSY0H5vvPQ3OLB6seBT0nPlH](https://lenovoau.service-now.com/alm_asset_list.do?sysparm_tiny=a40NNV76WSY0H5vvPQ3OLB6seBT0nPlH "https://lenovoau.service-now.com/alm_asset_list.do?sysparm_tiny=a40nnv76wsy0h5vvpq3olb6sebt0nplh")

18:05has context menu


One execution for PO update is pending


PS> Tracking request {"orderNoList":["SCTASK0572577"]} response : {	"msg":"No data found!",	"code":"400",	"data":[		{			"createdBy":"",			"createdData":"",			"errorSet":["PN 20Y4S0Y400  lack configuration; "],			"orderItem":"",			"orderNo":"",			"orderType":"",			"refDocItem":"",			"refDocNo":"SCTASK0572577",			"upsInfo":"",			"warehouse":""		}	]} status : 200

PS> Tracking request {"orderNoList":["SCTASK0572698"]} response : {	"msg":"No data found!",	"code":"400",	"data":[		{			"createdBy":"",			"createdData":"",			"errorSet":["ups call failed","{\"response\":{\"errors\":[{\"code\":\"121285\",\"message\":\"The postal code 27282 is invalid for ND United States.\"}]}}"],			"orderItem":"",			"orderNo":"",			"orderType":"",			"refDocItem":"",			"refDocNo":"SCTASK0572698",			"upsInfo":"",			"warehouse":""		}	]} status : 200

Hi @iqueipo 

  

This is SSC issue and we are transferring it to SSC IT team.

  

@itsupport  , Please transfer this ticket to SSC IT team.

  

@SSC team

  

Lenovo SMO has sent the payload for the tracking number but it didn’t get triggered from SSC. Could you please check it from your end? I have added the reference document number for your reference

  

Reference document number:

SCTASK0572577  
SCTASK0572620  
SCTASK0572698

![[Pasted image 20241212124807.png]]



1) Issue description: INC2024112000541: DaaS Production Issue Model.Name is missing in Asset table
2) Reporter Name: jchan19
3) Impacted Table: alm_asset
4) Account Name:  
5) Analysis:   
	- model.name is not available in asset table issue I checked for the logic to populate the name there is a br "Copy displayname to name" it is on before insert and condition company isNOTEMPTY.
	- There are 21 records out of wich there is 4 recent reocrds and 17 records are created in 2020
	- For the 4 recent records the company field is empty
	- and for those 17 records the reference is going to cmdb_model table
1) Impacted records: 21
2) Additional info required from the reporter: N/A.
3) Solution steps:



1) Issue description: INC2024120902366: SNOW need to move the status of the asset PF4D60WF in stock/available and remove it from the task SCTASK0571054

2) Reporter Name: mcorbalan
3) Impacted Table: alm_asset
4) Account Name:   fairstone
5) Analysis:   
	- - SCTASK0571054 is a COI order and the PF4D60WF asset has been picked up  because the State of the asset is ""**In Stock - Available*
	- They removed the PF4D60WF and processed the order with PF4D59MQ SN 
	- this caused the M2M asset PF4D60WF to deleted by the user "mcorbalan" from SCTASK0571054.  
	- Now the ask is to move the PF4D60WF back to the previous task.
7) Impacted records: 
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- Move the SN back to previous task as per reporter's request


Hi Eswar for the ahmid's ticket we discussed in today's DSM call he said Shunguo has asked us to re-tigger the in use status and in the comments ahmid has update as "Had discussed this with @epalla , and aligned that SNOW need to trigger the C05 code to SSC as per Shunguo request."  
Can you please confirm do we need to re-trigger C05 or 315 ?





1) Issue description: INC2024121002851: Remove the asset from TASK# SCTASK0571468
2) Reporter Name: bayyappa
3) Impacted Table: alm_asset
4) Account Name:   GT
5) Analysis:   
	- The ask here is to move the GM00VAW9 to its previous task SCTASK0515578.
	- SCTASK0571468 is a COI order and they want to process this task with different SN as this GM00VAW9 is open in another task in SSC.
	- They now want us to move the GM00VAW9 to SCTASK0515578.
1) Impacted records: 1
2) Additional info required from the reporter: N/A.
3) Solution steps:
	- Move the GM00VAW9 to SCTASK0515578
as we are replacing it with 



1) Issue description: SNOW   Need to deactivate the faulty device having SN# PF45ETDJ in SCTASK0348185 and swap it with a newly replacement device with SN# PF4XNCSQ and confirm
2) Reporter Name: 
3) Impacted Table:
4) Account Name:   
5) Analysis:   
	- Copy task has been done, SNOW IT to perform asset mapping.
	- The ask is to map 19 SN to Old task and one SN PF4XNCSQ to new task to 
SCTASK0570227
- After that, transfer this to MSCT to perform swap request and swap the faulty device having SN# PF45ETDJ and PF4XNCSQ
7) Impacted records: 
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- The ask is to map 19 SN to Old task SCTASK0348185 and map the SN PF4XNCSQ to new task SCTASK0570227

INC2024121302554 - LSP 


1) Issue description: INC2024121301744: service now Upload Onboard Part Number: Lenovo Device - Country Australia
2) Reporter Name: kganachari
3) Impacted Table: 
4) Account Name:  Multiplex
5) Analysis:   
	- Previously we had an incident :Multiplex AU and CA customers are not able to view the latest catalog items published from Lenovo for the contracts 6900005999, 6900005882 in Multiplex portal because of the Multiplex customized field named ‘Available in Country’ is empty.
	- Based on DS-13322 the manual activity of COT team was replaced by the automated solution available in the HW Model table. The ‘Available in Country’ will not be working as expected if the country received from Lenovo is in 3-digit format.
	- For this we proposed a permanent solution :
	  Whenever new contracts are created for Multiplex, COT team is requested to create a ITSM ticket and assign the same to SNOW IT to perform the 2-digit country code update and trigger/push the same to Multiplex customer.
	- Now the ask is New contract **6900009605** has been created kindly help to push the 2-letter country code to Multiplex system.
7) Impacted records: 
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- SNOW IT to perform the 2-digit country code update and trigger/push the same to Multiplex customer.


INC2024121602432 - for the mentioned 5 assets subscription end date to be 31 dec 2024 as these has been extended.
for the rest of 81 assets the subscription end date to be 36 months form the subscription start date.


1) Issue description:  : INC2024121701103: change the Subscription end dates as attached in the spread sheet
2) Reporter Name:  ka5
3) Impacted Table:  alm_asset
4) Account Name:  Cisco
5) Analysis:  
-  As per the current configurations the subscription end date in SNOW will be -1 day from LSP.
- Currently the Subscription end date is 2024-12-30 00:00:00 and Subscription end date should be 2024-12-31 00:00:00.
- For one record the Subscription end date is 2027-12-31 00:00:00 and Subscription end date should be 2024-12-31 00:00:00.
6) Impacted records:  1132 records
7) Additional info required from the reporter: NA 
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  Extra service
12) Solution Steps: Change the Subscription end dates as per the ask



1) Issue description: INC2024121602432: SNOW Subscription of attached devices are not showing correctly in DaaS SNOW, which needs to be corrected.
2) Reporter Name: psamal
3) Impacted Table: alm_asset
4) Account Name:  Cisco
5) Analysis:   
	- The ask is to update the Subscription end date as 31st Dec 2024 for billing purpose as the are still with the customer as per the reporter so they want to update the subscription end date for 5 assets.
	- This Cisco SK is offline billing as per the reporter and the u_subscription_order_number is 1234567890.
	- 
1) Impacted records: 
2) Additional info required from the reporter: N/A.
3) Solution steps:
	- Update the Subscription end date as per the ask


{

  "short_description": "Cisco unable to create rejection task for asset: FNJ7CVW056",

  "description": "Cisco unable to create rejection task for asset: FNJ7CVW056 and this task was manually created at Lenovo end",

  "asset_serial_number": "FNJ7CVW056",

  "rejection_reason": "rejected_delivery_issue",

  "external_task_number": "",

  "external_task_id": "",

  "lenovo_ritm_id": "8a91f3cec3f91a10c3624dd9d0013120",

  "lenovo_request_id": "ce91f3cec3f91a10c3624dd9d001311f",

  "attachment":  

  }


INC2024121802270 - 
For one asset PF3XT33C in transit is sent from SSC
PF3ZEME7 PF4ARDYM for this two the return order is created and posted to SSC and later moved to closed complete by CSC one jvaldez one by mcorbalan

INC2024073101381 sample ticket



1) Issue description: INC2024122001800: PWC MAc book - Device acceptance Date to be changed as 18th Dec
2) Reporter Name: nvenkatachal
3) Impacted Table: alm_asset
4) Account Name:   PWC
5) Analysis:   
	- The ask here is to update the Deemed accepted installed date (18th Dec 2024) & tranche (Dec tranche) to be updated by today.
	- This change is requested due to the original task falling within the December Tranche  - 2024 . to Close the  BSR within December tranche. As per the reporter
7) Impacted records: 52
8) Additional info required from the reporter: N/A.
9) Solution steps:
	-  Update the Deemed accepted, installed date (18th Dec 2024) & tranche (Dec tranche) to be updated.


INC2025010602152
1) Issue description: SNOW to change the end dates in SNOW for the below devices.
2) Reporter Name: jwong16
3) Impacted Table: alm_asset
4) Account Name:   Cisco
5) Analysis:   
	- As per the reporter the , subscription end date (12/30/2024) has ended
	- LOT has replied that they have extended these assets and it is Manual billing the ask here is to update the subscription end date as 1/31/2025 for the 5 SN and for the one SN with SO the ask is to change end date to 11/30/2027.
7) Impacted records: 6
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- Update the Subscription end date as per the ask.


Upon checking we could see that the Get contract items button is clicked twice within 10 seconds which resulted in the creation of duplicate records in the hardware intermediate table.

Also we could see that the bundle and hardware are present for the M75q ![[Pasted image 20250106191347.png]] 

1) Issue description: DaaS Production Issue Dublicate Cataloge items reflcting in intermediate table.(Priority)
2) Reporter Name: akhil
3) Impacted Table: Hardware intermediate
4) Account Name:   Orbia
5) Analysis:   
	- Upon checking the log we can find two outbound response log for the same contract, the Get contract items button is clicked twice within 5 seconds which resulted in the creation of duplicate records in the hardware intermediate table.
7) Impacted records: 
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- Remove the extra records as per the user's ask.