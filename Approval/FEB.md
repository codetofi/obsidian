

1) Issue description:
2) Reporter Name: 
3) Impacted Table:
4) Account Name:   
5) Analysis:   
	- 
6) Impacted records: 
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- 


Hi Eswar regarding INC2025012300086,
The issue here is the task moved to closed complete after customer acceptance.
Upon checking we could see that the task previously had an SN which was 


  
Upon checking we could see that the reason you weren’t able to add the SN under the asset section is because the SN is in “In Use” state but it should be in “In stock / available” state. The SN state was not moved to “In stock / available” because there was no return order task attached to this SN PF56WP3X. 
So in total there are two things:
For the SN to be available to in the asset section, it should be in "In stock/available" state but for this order the SN is in "In use" state.
 The SN is in "In use" state because there is no return order task attached to the SN.


1) Issue description: DaaS Production Issue Cisco || Order without POD REQ0193269
2) Reporter Name: ignacio
3) Impacted Table: alm_asset
4) Account Name:   Cisco
5) Analysis:   
	- Upon checking we could see that OVP has sent us the shipped status and shipment date after 2 hours of asset creation.
	- Due to which the shipment api has received an error as the shipment date was empty.
6) Impacted records: 1
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- Retrigger the Shipment and POD api

{"orderNoList":["SCTASK0608142"]} response : {  
"msg":"No data found!",  
"code":"400",  
"data":[  
{  
"createdBy":"",  
"createdData":"",  
"errorSet":["ups call failed","{\"response\":{\"errors\":[{\"code\":\"120302\",\"message\":\"Missing or invalid ship from address line 1\"}]}}"],  
"orderItem":"",  
"orderNo":"",  
"orderType":"",  
"refDocItem":"",  
"refDocNo":"SCTASK0608142",  
"upsInfo":"",  
"warehouse":""  
}  
]  
}


{"orderNoList":["SCTASK0608425"]} response : {  
"msg":"[SCTASK0608425] The order does not exist or has been deleted!",  
"code":"400",  
"data":[]  
}

	{"orderNoList":["SCTASK0608920"]} response : {  
"msg":"No data found!",  
"code":"400",  
"data":[  
{  
"createdBy":"",  
"createdData":"",  
"errorSet":["ups call failed","{\"response\":{\"errors\":[{\"code\":\"120302\",\"message\":\"Missing or invalid ship from address line 1\"}]}}"],  
"orderItem":"",  
"orderNo":"",  
"orderType":"",  
"refDocItem":"",  
"refDocNo":"SCTASK0608920",  
"upsInfo":"",  
"warehouse":""  
}  
]  
}

{"orderNoList":["SCTASK0607581"]} response : {  
"msg":"No data found!",  
"code":"400",  
"data":[  
{  
"createdBy":"",  
"createdData":"",  
"errorSet":["PN 20Y4S0Y400 lack configuration; "],  
"orderItem":"",  
"orderNo":"",  
"orderType":"",  
"refDocItem":"",  
"refDocNo":"SCTASK0607581",  
"upsInfo":"",  
"warehouse":""  
}  
]  
}



1) Issue description: INC2025020401150: DaaS Production Issue Cisco || US order rejected REQ0188280
2) Reporter Name: Ignacio
3) Impacted Table: alm_asset
4) Account Name:  Cisco
5) Analysis:   
	- As per the reporter, This US order was rejected by Cisco as the laptop was LIT by UPS. We didn´t receive the rejection task in our end.
	- The SN under this order is deemed accepted in our system as the actual delivery date is 2025-01-14.
	- The ask here is to create the rejection task in our end.
6) Impacted records: 1
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- Change the acceptance state of asset to rejected and create the rejection task in our end


{

  "short_description": "Cisco unable to create rejection task for asset: L63H9JPX62",

  "description": "Cisco unable to create rejection task for asset: L63H9JPX62 and this task was manually created at Lenovo end",

  "asset_serial_number": "L63H9JPX62",

  "rejection_reason": "POD",

  "external_task_number": "",

  "external_task_id": "",

  "lenovo_ritm_id": "dded9db3c33a1210aeaad71a050131d7",

  "lenovo_request_id": "55ed9db3c33a1210aeaad71a050131d7",

  "attachment":  

  }


Hi team,

Upon checking there are 239 present for these return order tasks out of which only two are in In stock wiped state. For those two SN we have re-triggered the Disk-wipe certificate.
The asset needs to be in In stock wiped state for us to trigger the blancco certificate.
This status is updated from SSC to SNow.


Upon checking out of the 24


Previoulsy Lenovo SNow was different api to fetch the Disk wipe certificate from Blanco which was causing error after which this process was improved and blanco provided with a different api and now it is working fine. 

As for the SN for which the Disk wipe is not available in SNow we will retrigger the Disk wipe for the SN.

Hi team as per checking out of the 239 SN, One SN is in in use state as it was updated as device purchase by LOT and as per the request by cisco it has been updated as in use.

For the rest of the SN we have received wiped status for 203 SN and for the rest of 35 SN wiped status has not been sent from SSC. 
We have triggered the Blanco cert for those 203 SN. SSC/CFS needs to align the disk wipe process state and sub state for the 35 SN in SSC and trigger it to SNow.
I've sent the attachment over the email.


MJ0F0AGY -  in use

PF2FL2MF - wiped came (in 2022)



1) Issue description:INC2025020701460: DaaS Production Issue AU Return Order Blancco Cert Missing
2) Reporter Name: Carmen
3) Impacted Table: sc_task
4) Account Name:   Cisco
5) Analysis:   
	- As per the reporter the return order task are missing the disk wipe certificate attachment.
	- Upon checking we could see that the task have the payload.xml attachment but we didn't receive disk wipe attachment.
	- The disk wipe certificate are now available in Blanco portal.
	- We have asked cisco to align the tasks in order to retrigger the certificate and received the confirmation.
6) Impacted records: 24
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- Need to re-trigger the disk wipe certificat



1) Issue description: DaaS Production Issue KPMG AU DaaS - Subscription Start/End Date  
2) Reporter Name: Lganasen  
3) Impacted Table: alm_asset  
4) Account Name: KPMG  
5) Analysis:  
- For some SN where there is a difference in Subscription end date, the system has calculated the end date as per the logic where it gets the difference of the contract start and end date and adds it to the subscription start date.
- But in some contracts the start date and end date have a difference of 2 years while the term is 36. 
- COT has updated the contract as per the term.
- Need to update the subscription end date in SNOW as per the Subscription end date in LSP.  
1) Impacted records:  
2) Additional info required from the reporter: N/A.  
3) Solution steps:  
- Need to update the subscription end date in SNOW as per the LSP data provided by the reporter.



u_contractnumber=6900008970^u_mainserializeditem=Y^ORu_productcategoryLIKEHW^u_higheritemnumber={1}

Error:
SCTASK0623263
{"timestamp":"2025-02-18T06:43:57.691+00:00","path":"/recurringrevenue/subscription/v1/orders/daas-order","status":404,"error":"Not Found","requestId":"0ba84e80-755765"}

SCTASK0623260
{"timestamp":"2025-02-18T06:43:11.163+00:00","path":"/recurringrevenue/subscription/v1/orders/daas-order","status":404,"error":"Not Found","requestId":"c04b374e-755574"}




Upon checking we could see that the Return order has been attached to the SN on 2025-02-06.
SO The state is moved for In use to In Transit, Assed direction has been moved to "Return to ware house"
As per the history of the SN the on 2025-02-17 the state and sub state of the SN have been updated to in use and the asset direction is removed.

After which SSC has again updated the SN state to In Transit and as per the discussion with the team since the asset direction is empty at this time because it was removed previously, the order status has been changed to shipped and the task has been moved to WIP.


INC2025021901858 - disk wipe completed has been updated due to some fix script run.


u_contractnumber=6900004245^u_mainserializeditem=Y^ORu_productcategoryLIKEHW^u_higheritemnumber=1

[457d93f787656510762f85d50cbb3517
,0f3e5ffb87656510762f85d50cbb35fa ,
6165c6d1db026dd0c6b253dbd39619c4,
9265c215db026dd0c6b253dbd3961999
unflexDays]

account=457d93f787656510762f85d50cbb3517^ORaccount=0f3e5ffb87656510762f85d50cbb35fa^u_asset_picked=false^install_status=6^substatus=available^model=6165c6d1db026dd0c6b253dbd39619c4^ORmodel=9265c215db026dd0c6b253dbd3961999^u_task_number.stateIN3,4,7^

NQaccount=457d93f787656510762f85d50cbb3517^ORaccount=0f3e5ffb87656510762f85d50cbb35fa^u_asset_picked=false^install_status=6^substatus=Available-Inactive^model=6165c6d1db026dd0c6b253dbd39619c4^ORmodel=9265c215db026dd0c6b253dbd3961999^u_task_number.stateIN3,4,7^u_flex_start_dateRELATIVELT@dayofweek@ago@0



INC2025022000838 - Subscription start date is populated on asset level based on the  Subscription start date of the task. In task level subscription start date is calculated It first retrieves the tranche record matching the current `u_tranche_id` and extracts its `u_end_date`. Using `GlideDate`, it determines the total days in that month and the current day, then adds the required days to move to the **1st of the next month**. Finally, it sets this calculated date as `u_subscription_start_date`.





4) Issue description: DaaS Production Issue PwC AU- PF5D8EEZ status in SSC to be amended
5) Reporter Name: Ling yap
6) Impacted Table: alm_asset
7) Account Name:   PWC
8) Analysis:   
	- Upon checking we could see that the return order has been attached to this SN before the order drop task has been moved to closed complete because they wanted to attach this SN to COI order.
	- They were unable to attach this SN to COI as the SN was present in open order, Now the COI is cancelled and as per SMO they want to bill the order drop task as it is still in PWB.
	- The ask here is to update the acceptance and actual delivery date that were removed when Return order was attached.
9) Impacted records: 1
10) Additional info required from the reporter: N/A.
11) Solution steps:
	- Needs to revert back the POD and acceptance
	- Need to transfer to LOT to update tranche


da

12) Issue description: INC2025021901858: DaaS Production Issue Asset PF2TLCRT disk wipe failed on SSC, but why SNOW resolution update as 'Disk Wipe Completed' and asset substate not updated as 'Wipe Failed'
13) Reporter Name: Jwong
14) Impacted Table: sc_task
15) Account Name:   Cisco
16) Analysis:   
	- Assets are disk wipe failed on SSC. In SNOW updated resolution 'Disk Wipe Completed'.  
This happened because we tried to disk wipe certificate for asset under different incident and flow got triggered and updated the resolution.
17) Impacted records: 1
18) Additional info required from the reporter: N/A.
19) Solution steps:
	- Need to update resolution on task level to previous value


Analysis:

C05 bulk is not triggered to SSC for the SN PF3AJJS9 as the status was not deemed accepted and the deemed acceptance did not happed because the pod api was not executed for this SN. 
Further investigating we could see that the POD api has been triggered for this SN but received Serial number does not exist is Cisco.




20) Issue description:INC2025021802805: DaaS Production Issue Missing SSC return order number
21) Reporter Name: agagiu
22) Impacted Table: alm_asset
23) Account Name:   Cisco
24) Analysis:   
	- C05 bulk is not triggered to SSC for the SN PF3AJJS9 as the status was not deemed accepted and the deemed acceptance did not happed because the pod api was not executed for this SN as this is a replacement SN. 
	-  Further investigating we could see that the POD api has been triggered for this SN but received Serial number does not exist is Cisco.
25) Impacted records: 1
26) Additional info required from the reporter: N/A.
27) Solution steps:
	- Need to retrigger C05 to SSC and align accordingly.
	- Mail Cisco and align with them and re trigger the POD api





Hi Meeta, 

This ticket was initially raised why local currency is being sent to EGISS. After analysis We've updated the analysis on 14th as follows, 

The currency sent via the payload for the order drop task numbers is working as expected. As per the logic, it uses the cost currency of the order drop task's product model and, if applicable, the respective white glove task's product model, which is determined based on the parent account's currency.
Upon checking we could see that the currency has been updated to USD in parent account.

Since the currency has been update as USD in Parent account, we transferred the ticket to COT and COT updated the cost currency in model as USD. 

Now as per COT the exchange rate should not be there in the hardware model.
As a work around we'll have to remove the Exchange rate, from currency, to currency, old exchange rate and valid from model and contract.



Hi Meeta,

Regarding INC2025021900787 || CISCO - US || HJFTGW3KX3 & C02FPJ8XMD6M - missing contract info. 
As per MSCT,
Cisco has reported the aforementioned assets within their possession. However, it has not tied to any REQ. They need SNow IT to assist them to re-open the Request/RITM/Task. 



1) Issue description: INC2025022401242: DaaS Production Issue SN details has not been updated due to Shipment/POD API not executed

2) Reporter Name: mzahari
3) Impacted Table: alm_asset
4) Account Name:   Cisco
5) Analysis:   
	- Upon checking we could see that OVP has sent us the shipped status and shipment date after 2 hours of asset creation.
	- Due to which the shipment api has received an error as the shipment date was empty.
6) Impacted records: 7
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- Retrigger the Shipment and POD api

	
HJFTGW3KX3 SN was delivered to customer under SCTASK0295265 and later its updated as DND.
C02FPJBLMD6M - REQ1087408 / EXT REQ0026318 (Order was been rejected but the laptop got shipped) and upon checking we could see now it is deleted on 2021 in SNow and we're able to find in deleted records.


Hi Stephen,

Missing/Lost has been updated by LOT team.

For Request REQ0200567 One SN is in Missing/Lost and rest 2 SN are in In use but the account tagged for these asset is Cisco Systems, Inc where as the account tagged in the request is Cisco Systems Canada Co.

For REQ0200582 13 SN are in In use and the account tagged in the asset is different from account tagged in Request rest 2  are in In transit.

For REQ0200874 all the SN are in In Transit.



INC2025022401214 -
C02F45NBMD6M SN has been attached to a return order SCTASK0507670 on 2024-08-19 and it was not processed to SSC so the SN state remained in In use state. 
Later One more return order SCTASK0562686 has been created and attached to this SN, and this time it was processed to SSC and the In transit state was triggered to SSC successfully.

After which again SCTASK0507670 has been mapped to this SN and processed on 2025-02-11 and the SN state is moved to In transit and SSC has sent us state mismatch error.

For this SN PF39WZCW Return order task SCTASK0456000 is attached andIn transit processed to SSC and we haven't received any updates for this SN from SSC after this.