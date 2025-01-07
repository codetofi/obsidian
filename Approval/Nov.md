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

1) Issue description: INC2024111201191: SNOW ITSM / Tech Mahindra Italy / exchange rate update
2) Reporter Name: llukacova
3) Impacted Table:
4) Account Name:   Tech Mahindra
5) Analysis:   
	- The ask is to update the exchange rates for new onboarded customer customer Tech Mahindra Italy (1217838991). The CMR was updated, due to this change the new task have new exchange rates. We need to keep the same prices as they were when customer placed the orders under old entity.
	- to expedite the exchange rate update as LOT would need to process for Tech Mahindra Italy billing from Jan '23 - Nov'24 (impacted amount ~USD 210K).
6) Impacted records: 
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- Schedule a call and update the exchange rate.



  
1) Issue description: INC2024111102867: DaaS Production Issue SN PC2AG2N4 Status Needs to Change - 'In Use'
2) Reporter Name: lhustavova
3) Impacted Table: alm_asset
4) Account Name:  Grant Thornton UK
5) Analysis:   
	- SSC had updated the status to In Use in SSC and MSCT had reverted the Shipment/Delivery date and status to In use for PC2AG2N
7) Impacted records: 1
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- Snow IT to update the acceptance status for PC2AG2N4.



6900005215
6900005219
6900007081
6900008834
6900009082




6900009082
6900008835
6900008834



INC2024111302163 - DaaS Production Issue IT issue - condition reports need to be pushed to Cisco to the correct tasks

There were 731 asset review condition task given out of which 98 were created after the condition automation was moved to production and we have sent them to cisco it is working as expected, for 633 history records which were created before the update, we asked cisco to remove condition reports and got the confirmation and now we have to push the reports to cisco for the correct cisco return task.

There were 731 asset review condition tasks, out of which 98 were created after the condition report automation was moved to production. We have sent them to Cisco, and they are working as expected. For the 633 historical records that were created before the update, we asked Cisco to remove the condition reports and received confirmation. Now, we have to push the reports to Cisco for the correct Cisco return tasks.

1) Issue description: INC2024111302163 - DaaS Production Issue IT issue - condition reports need to be pushed to Cisco to the correct tasks
2) Reporter Name: zpodolska
3) Impacted Table: alm_asset
4) Account Name:   Cisco
5) Analysis:   
	- There were 731 asset review condition tasks, out of which 98 were created after the condition report automation was moved to production.We have sent them to Cisco, and they are working as expected.
	-  For the 633 historical records that were created before the automation was moved, we asked Cisco to remove the condition reports and received confirmation. 
	- Now, we have to push the reports to Cisco for the correct Cisco return tasks.
7) Impacted records: 633
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- For the 633 historical records that were created before the automation was moved, we asked Cisco to remove the condition reports for the SN and received confirmation. Now, we have to push the reports to Cisco for the correct Cisco return tasks.



1) Issue description: INC2024111401713: Service now PC2AFZ7A status is incorrect
2) Reporter Name: pquirk
3) Impacted Table: alm_asset
4) Account Name:   GT
5) Analysis:   
	- PC2AFZ7A has been physically returned to UK CFS, but we are unable to receive it in SSC because its current status is in correct. It needs to be ‘In Transit’.  It is currently ‘In Stock/Delivered
	- As we checked this is a history record and 315 has not been triggered as the logic was moved on July 2023 because of which 313 has received incorrect status error.
	- We should trigger 315 and then 313 to change it to the correct status.
7) Impacted records: 1
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- Trigger "in use" and then "in transit" to SSC.


INC2024111501930
INC2024111800510
INC2024111400368

1) Issue description: 	INC2024111400368 DaaS Production Issue CISCO - IN: SNow IT to investigate why some asset Missing Acceptance status: REQ0173857 & REQ0173876
   Similar issue:
	INC2024111501930
	INC2024111800510
	
2) Reporter Name: sedward1
3) Impacted Table: alm_asset
4) Account Name:   Cisco
5) Analysis:   
	- Initially the acceptance status was missing and it got updated afterwards.
	- Install date was updated based on the scheduled run date.
	- Now the ask is to update the Install date based on Actual delivery date as currently it is 18 Nov.
	- They want us to update install date according to the actual delivery date i.e Cisco acceptance date 10BD upon Delivered.
7) Impacted records: 16
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- Update the install date according to the actual delivery date.


1) Issue description: INC2024111801453: DaaS Production Issue PWC - Bulk upload Request for Apple devices failed in customer portal - REQ0180112
2) Reporter Name: ss51
3) Impacted Table: sc_request
4) Account Name:   
5) Analysis:   
	- As we checked, the email that you have used in the RITM attachment does not satisfy the condition for Global user criteria and only satisfy the condition for bangalore user criteria.
	- But since in the transform map on before script we are checking only one user criteria that picks the Global user criteria out of the two user criterias and since the email does not satisfy the condition for global user criteria, the records are not getting proceINC2024112000541ssed.
7) Impacted records: 34
8) Additional info required from the reporter: N/A.
9) Solution steps:
	
- https://lenovoau.service-now.com/sys_transform_map.do?sys_id=aded51ff1b6b7510f3e264a8b04bcb50&sysparm_record_target=sys_transform_map&sysparm_record_row=1&sysparm_record_rows=3&sysparm_record_list=nameCONTAINSpwc%5EORDERBYDESCsys_created_on


- Ask them to cancel and re drop the order.
	- Ask them to send an email to Meeta and get approval for entity change
temp :
T14 R7- only item price changed and reverted.
T14 Ryze - Only monthly price changed and reverted.



1) Issue description: INC2024111900685 DaaS Production Issue Asset condition report deficiency code partially missing.
2) Reporter Name: jchan19
3) Impacted Table: u_ssc_check_list
4) Account Name:  cisco
5) Analysis:   
	- Based on Jira DS-16404, the length for the description has been prolong however in the report it still missing.
	  - Upon checking we can see that the deficiency description has not updated in the u_ssc_check_list.
	  - SNOW IT to update the field with the missing description.
7) Impacted records: 3
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- SNOW IT to update the field with the missing description.



INC2024111400368 -  check the logs and I checked it there is no log of the Scheduler on 15 and 16. Only one asset has been accepted on 15th by scheduler.


INC2024111800510 - POD api was executed on 2024-11-07 and on 2024-11-08 it got deemed accepted. SNOW it to update correct Acceptance and Install Date based on Actual Delivery Date.


INC2024111501930 - 2024-11-13 Pod uploaded 2024-10-10 Actual delivery date, Some got accepted on 14 some got accepted on 17 and some got accepted on 18
Checked for log on 15th and 16th no log found for both task.


|          |
| -------- |
| PF4XNF5Z |
| PF4XNHEC |
| PF4XNHBH |
| PF4XPQCT |

|          |
| -------- |
| PF4XPQEQ |
| PF54E6V1 |
| PF4XNF5K |
| PF4XNHCH |
| PF54E6VP |
| PF4XPQD9 |
| PF4XNHCQ |
| PF4XNHC1 |
| PF4XNF50 |


1) Issue description:INC2024111800510 DaaS Production Issue CISCO-AU: SNow IT to update correct Acceptance and Install Date based on Actual Delivery Date: REQ0173075 / REQ4886558 / SCTASK0519819
2) Reporter Name: sedward1
3) Impacted Table: alm_asset
4) Account Name:   CIsco
5) Analysis:   
	- POD api was executed on 2024-11-07 and on 2024-11-08 it got deemed accepted. 
	- SNOW it to update correct Acceptance and Install Date based on Actual Delivery Date.
1) Impacted records: 68
2) Additional info required from the reporter: N/A.
3) Solution steps:
	- SNOW it to update correct Acceptance and Install Date based on Actual Delivery Date.



INC2024112002571 - S


1) Issue description: INC2024112200479: help map the assets which are provided in attached sheet to SCTASK0561297
2) Reporter Name: svashisht
3) Impacted Table: sc_task
4) Account Name:   Adastria 
5) Analysis:   
	-  SCtask  SCTASK0561297 has 497 assets but Customer needs billing for attached 180 assets for December. Copy task is done. We want to keep 180 assets in this new SCTASK0561297. Remaining assets need to be mapped to old SCTask ID SCTASK0481012
7) Impacted records: 180
8) Additional info required from the reporter: N/A.
9) Solution steps: 
	- SNOW IT to keep 180 assets in this new SCTASK0561297 and map 317 assets to old task SCTASK0481012.



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




1) Issue description: INC2024111801914: DaaS Production Issue Need to add new contract 6900009167 & Sold To 1217913881 on this Snow Request REQ0162835
2) Reporter Name: mimran6
3) Impacted Table: sc_task, sc_req_item, sc_request
4) Account Name:   
5) Analysis:   
	- Initially the ask was to to update the new contract in the hardware model as it had another contract and they wanted to bill this with the new contract.
	- As it is not the BAU process we asked for LOT intervention.
	- The old contract that was present in the model is having different account and the new contract given is having a different account.
	- As per LOT, the we need to map the account with the new contract in  REQ,SCTASK,M2M,Asset, RITM levels.
	- Model mapping with new contract -- LOT
	  
6) Impacted records: 5
7) Additional info required from the reporter: N/A.
8) Solution steps: 
	-  Need to map the Account at REQ,SCTASK,M2M,Asset, RITM levels. --- SNOW IT
	-  Model mapping with new contract --- LOT




1) Issue description: DaaS Production Issue Red cross AU- Wrong SN PF3FR4WA attached to SCTASK0561203. Move back to SCTASK0266060
2) Reporter Name: ytan7
3) Impacted Table: sc_task
4) Account Name: Red Cross Australia
5) Analysis: 
	- SCTASK0561203 is a COI order and the PF3FR4WA asset has been picked up  because the State of the asset is ""**In Stock - Available*
	- They removed the PF3FR4WA and processed the order with PF3ETNF8 SN and the order has been processed with this SN.
	- this caused the M2M asset PF3FR4WA to deleted by the user "wxu3" from SCTASK0561203.  
	- Now the ask is to move the PF3FR4WA back to the SCTASK0266060 task
6) Impacted records: 1 deleted record - PF3KERJL
7) Additional info required from the reporter: NA
8) Proposed temporary solution: Same as Solution steps
9) Permanent Solution: NA
10) Cause of the issue (RCA): Requests-Special biz scenario support
11) Issue Type: DaaS | Manual Intervention | Customer/CSC-Asset Management
12) Solution Steps: 
	- To recover the deleted record PF3FR4WA from the Deleted records
	- And remap the asset PF3FR4WA back to theSCTASK0266060  as per the reporter's request.
	

INC2024112002571 - https://lenovoau.service-now.com/sys_transform_map.do?sys_id=6ce108201bd2a4108a5977331d4bcb59&sysparm_record_target=sys_transform_map&sysparm_record_row=1&sysparm_record_rows=2&sysparm_record_list=nameCONTAINSthird%5EORDERBYDESCsys_created_on


INC2024112501287 - The are 56 task and tranche id is not populated for 2 of them and there are 973 assets in these task (but only 963 are given in excel) 
None of these assets contain tranche id and we have two br to populate tranche id 
- Update Tranche ID on Asset (created after the assets were created and afte the tranche updatd on task)and -
- Populate Tranche on Asset (runs on asset tabel after it gets accepted and looks for tranche and updates it but after looking we could see that all the tranche have been created on 2024)


1) Issue description:service now De-activate or removal of the line item 5TS1B66185 -CFS Asset Tag - Ext Box Label
2) Reporter Name: uv2
3) Impacted Table: cmdb_hardware_model
4) Account Name:   ACT WoG
5) Analysis:   
	- After creating the contract 6900009482 for ACT Digital, Data and Technology Solutions Centre – AU and when pulled in snow the below service line item is appearing twice in Snow.
	- Where as in LSP it is uploaded correctly according to the reporter.
	-
 https://www.textcompare.org/xml/?id=674808821e087b10dd5a7f64
7) Impacted records: 
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- 


INC2024112002342 - Query -
stateNOT IN3,4,7,273^u_ssc_return_order_numberISEMPTY^account.nameLIKEcisco^u_task_type=Return Order^ORDERBYDESCsys_created_on

u_task.numberINSCTASK0561395,SCTASK0561394,SCTASK0561393,SCTASK0561392,SCTASK0561390,SCTASK0561389,SCTASK0561388,SCTASK0561387,SCTASK0561386,SCTASK0561385,SCTASK0561384,SCTASK0561383,SCTASK0561382,SCTASK0561381,SCTASK0561380,SCTASK0561379,SCTASK0561378,SCTASK0561377,SCTASK0561376,SCTASK0561375,SCTASK0561374,SCTASK0561373,SCTASK0561372,SCTASK0561371,SCTASK0561370,SCTASK0561369,SCTASK0561368,SCTASK0561367,SCTASK0561366,SCTASK0561365,SCTASK0561363,SCTASK0561362,SCTASK0561361,SCTASK0561360,SCTASK0561359,SCTASK0561358,SCTASK0561357,SCTASK0561356,SCTASK0561355,SCTASK0561354,SCTASK0561353,SCTASK0561352,SCTASK0561351,SCTASK0561350,SCTASK0561349,SCTASK0561348,SCTASK0561347,SCTASK0561346,SCTASK0561345,SCTASK0561344,SCTASK0561343,SCTASK0561341,SCTASK0561340,SCTASK0561339,SCTASK0561337,SCTASK0561338,SCTASK0561336,SCTASK0561335,SCTASK0561334,SCTASK0561333,SCTASK0561332,SCTASK0561331,SCTASK0561330,SCTASK0561329,SCTASK0561328,SCTASK0561327,SCTASK0561326,SCTASK0561325,SCTASK0561324,SCTASK0561323,SCTA...36843,SCTASK0436842,SCTASK0436840,SCTASK0436839,SCTASK0436838,SCTASK0436837,SCTASK0436836,SCTASK0436835,SCTASK0436834,SCTASK0436833,SCTASK0436832,SCTASK0436831,SCTASK0436830,SCTASK0436829,SCTASK0436828,SCTASK0436827,SCTASK0436826,SCTASK0436825,SCTASK0436824,SCTASK0436823,SCTASK0436822,SCTASK0436821,SCTASK0436820,SCTASK0436819,SCTASK0436818,SCTASK0436817,SCTASK0436816,SCTASK0436815,SCTASK0436814,SCTASK0436813,SCTASK0436812,SCTASK0436809,SCTASK0436808,SCTASK0436807,SCTASK0436806,SCTASK0436805,SCTASK0436804,SCTASK0436802,SCTASK0436801,SCTASK0436800,SCTASK0436799,SCTASK0436798,SCTASK0436797,SCTASK0436796,SCTASK0436795,SCTASK0436794,SCTASK0436793,SCTASK0436792,SCTASK0436791,SCTASK0436790,SCTASK0436789,SCTASK0436788,SCTASK0436787,SCTASK0436786,SCTASK0436785,SCTASK0436784,SCTASK0436783,SCTASK0436782,SCTASK0436781,SCTASK0436780,SCTASK0436779,SCTASK0436778,SCTASK0436777,SCTASK0436776,SCTASK0436775,SCTASK0436774,SCTASK0436773,SCTASK0436772,SCTASK0436771,SCTASK0436770,^ORDERBYDESCsys_updated_on



Hi @Meeta,
Good day!
This is regarding INC2024111801453.
Issue： Bulk upload Request for Apple devices failed in customer portal.

Analysis:
- Upon checking we could see that As per the current logic, at present only one user criteria for PwC bulk orders is taken if the user raises the request for that catalog item.
- But for the catalog item we are having two user criteria:
	1. Global user criteria 
	2. Bangalore user criteria
	The email-id provided in the bulk order RITM attachment is satisfying the condition for the Bangalore user criteria but does not satisfy the condition for Global user criteria.
	Since the system will pick only one user criteria, the global user criteria is getting into the loop first because of which the request is getting failed.

We wanted to check with you for this issue whether a technical Jira story needs to be raised or Jira story needs to be raised for the permanent fix.



This has been created by COT as they have with different email ids for each city.



1) Issue description: Service Now Cisco SN in wrong status in SSC x 2
2) Reporter Name: pquirk
3) Impacted Table: alm_asset
4) Account Name:  Cisco
5) Analysis:   
	-  PF3024SW has been physically returned to UK CFS, but we are unable to receive it in SSC because its current status is in correct. It needs to be ‘In Transit’.  It is currently ‘Ship to customer" in SSC
	- As we checked this is a history record and 315 has not been triggered as the logic was moved on July 2023 because of which 313 has received incorrect status error.
	- We have another SN TKWPX7TCW4 SSC is checking why its not in in transit.
6) Impacted records: 
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- As per SSC, they have asked us to trigger the in use status and will check with them for in transit status



1) Issue description: INC2024112800534: DaaS Production Issue MYOB NZ - update installation dates of devices
2) Reporter Name: sdaud1
3) Impacted Table: alm_asset
4) Account Name:   MYOB
5) Analysis:   
	- The ask is to update the installation date of SCTASK0554366 (17 devices) to 20-Nov-2024 (UTC 00) for LOT to proceed with billing
	- It is currently in 2024-11-28
1) Impacted records: 17
2) Additional info required from the reporter: N/A.
3) Solution steps:
	-  update the installation date of SCTASK0554366 (17 devices) to 20-Nov-2024 (UTC 00) for LOT to proceed with billing
	  


Hi Meeta we have an ITSM to change access from external to internal user, for this we need to add the user - Joseph Karam(jkaram@lenovo.com) in Lenovo CSC group.
Do we need to raise a WO for this or shall we proceed with this ITSM.


Hi team, 
As per the internal discussion, 
The original ask for PWC was only global user will create, then why was this banglore user criteria created? As these were created by COT team we would like COT team intervention to check on this.

CS0098038
CS0098044
CS0098043
HP Schedule creation: request : "<am:fault xmlns:am=\"http://wso2.org/apimanager\"><am:code>101500</am:code><am:type>Status report</am:type><am:message>Runtime Error</am:message><am:description>Error in Sender</am:description></am:fault>"



Cisco SCM (Thailand) Ltd	- https://lenovoau.service-now.com/cmn_location_list.do?sysparm_query=account.sys_id%3D8a40964bdb7a30100adc96bad396194b&sysparm_first_row=1&sysparm_view=

Hi team, Below are the links for the location table.


Cisco SCM (Thailand) Ltd View - https://lenovoau.service-now.com/cmn_location_list.do?sysparm_query=account.sys_id%3D8a40964bdb7a30100adc96bad396194b&sysparm_first_row=1&sysparm_view=

Cisco Systems (Taiwan) Ltd - https://lenovoau.service-now.com/cmn_location_list.do?sysparm_query=account.sys_id%3D7481e183dbfa785086898a1705961932&sysparm_first_row=1&sysparm_view=


Cisco Systems Management B.V. PH - https://lenovoau.service-now.com/cmn_location_list.do?sysparm_query=account.sys_id%3D1bb00153db35f410dc3912e21496195e&sysparm_first_row=1&sysparm_view=


Cisco Systems Thailand Ltd - https://lenovoau.service-now.com/cmn_location_list.do?sysparm_query=account.sys_id%3Dd9f7e9c3dbb230100adc96bad39619f4&sysparm_first_row=1&sysparm_view=



1) Issue description: DaaS Production Issue CISCO - EMEA: SNow IT to update quantity in RITM and Task level as Partner has reduced dispatch qty due to stock constrain
2) Reporter Name: sedward1
3) Impacted Table: sc_req_item
4) Account Name:   cisco
5) Analysis:   
	- Reducing in total qty dispatch to customer due to stock constraints. In order to avoid the billing process issue.
	- Now the ask is to update the updated quantity in RITM and task level.
1) Impacted records: 
2) Additional info required from the reporter: N/A.
3) Solution steps:
	-  Update the updated quantity in RITM and task level.



1) Issue description: INC2024112901019: DaaS Production Issue KPMG NZ - Activation request assign to LOT team
2) Reporter Name: uchinnasamy 
3) Impacted Table: alm_asset,sc_task
4) Account Name:   KPMG NZ
5) Analysis:   
    - Initially this ticket was created to assist for the activations as per the attached sheet.
    - Later the reporter asked to hold the ticket to SNOW IT for some update.
	- The ask is to update the Device Installed date  25 Nov 2024 and
	  Device Accepted date 25 Nov 2024.
	 - Currently the date is 2024-11-29.  
	 - Reason for the update as per the reporter:  cut-off date for KPMG NZ is 25th Nov.
7) Impacted records: 238 SN and 3 task
8) Additional info required from the reporter: N/A.
9) Solution steps:
	- update the Device Installed date  25 Nov 2024 and
	  Device Accepted date 25 Nov 2024.


Hi Meeta,
Good day

This is regarding INC2024111801914.
We have you email approval for the entity mapping over the email and we wanted to confirm with you can we proceed with the execution for the entity mapping.
Thanks.


Hi team, upon checking a sample record we could see that the price for the contract 6900003552 are aligned as per the excel provided in the RITM.

![[Pasted image 20241129184002.png]]
![[Pasted image 20241129184346.png]]![[Pasted image 20241129184603.png]]

Kindly let us know what is the issue here.


Jchan ticke - SCTASK0471554 this task has disk wipe checking found by checking with u_desc true.


Unable to view catalog item refrence ticket - INC2024050801025 

![[Pasted image 20241130225105.png]]

![[Pasted image 20241130225211.png]]

![[Pasted image 20241130231510.png]]

![[Pasted image 20241130231529.png]]
![[Pasted image 20241130231619.png]]
![[Pasted image 20241130231638.png]]

![[Pasted image 20241130231716.png]]

![[Pasted image 20241130231740.png]]

![[Pasted image 20241130231823.png]]

![[Pasted image 20241130231839.png]]

All of the bundles have been sent to cisco and received success response.

1) Issue description: INC2024112002342: DaaS Production Issue Missing diskwipe attachment.
2) Reporter Name: jchan19
3) Impacted Table: sc_task
4) Account Name:   cisco
5) Analysis:   
	- The reporter has provided a report with condition stateNOT IN3,4,7,273^u_resolutions=Disk Wipe Completed^u_has_blancco_attachment=false
	- upon checking none of the asset are having blanco certificate
	- And the number of tasks is changing everytime.
1) Impacted records: 
2) Additional info required from the reporter: N/A.
3) Solution steps:


INC2024120202739 - For the 877 de activation the subscription end date has been updated as it met the condition for the scheduler on 29th
INC2024120300279 - The state change is not happened due the the error status code received in the reponse. 
- Need to check why the triggering has been done twice for 7 tasks out of 8
- Need to chech when and where are we creating the rr_model_middelware
- Need to check wiht the reporter why has he closed completed some of the task and not these


Hi Meeta,  

Good day!  
This is regarding INC2024111801453. 
  
Issue: Bulk upload request for Apple devices failed in the customer portal.

Analysis:
- Upon checking we could see that As per the current logic, at present only one user criteria for PwC bulk orders is taken if the user raises the request for that catalog item.
- But for the catalog item we are having two user criteria:
	1. Global user criteria 
	2. Bangalore user criteria
	The email-id provided in the bulk order RITM attachment is satisfying the condition for the Bangalore user criteria but does not satisfy the condition for Global user criteria.
	Since the system will pick only one user criteria, the global user criteria is getting into the loop first because of which the request is getting failed.
**UPDATE:**
- We connected with the reporter and asked him to create order with the global user email but the request got failed again.
- This is because in the on before script we are validating if the catalog item's vendor (PRICEWATERHOUSECOOPERS SERVICE DELIVERY CENTER (BANGALORE) PRIVATE LIMITED) is same as the user's company(PricewaterhouseCoopers Ltd (India)PWC- HQ) whose email has been used in the the excel attachment.



As for PC2755MH we checked in SNOW and we have Return order - 	
SCTASK0556630 and we have  triggered 313 on and received the following error.  


{	"code":"400",	"data":{},	"description":"PC2755MH Incorrect status",	"errorCode":"",	"success":false}


{

              "code":"400",

              "data":"",

              "description":"bin quantity locking! Please try again later",

              "errorCode":"",

              "success":false

}
PC2AG2Y4-In Use
PC2755MH- In Stock/Delivered’


1) Issue description: INC2024120302642: SNOW Unable to Book In PC2755MH and PC2AG2Y4
2) Reporter Name: pquirk
3) Impacted Table: alm_asset
4) Account Name:   GT
5) Analysis:   
	- Upon checking As for PC2755MH we checked in SNOW and we have Return order - 	
SCTASK0556630 and we have  triggered 313 on and received the following error.  
- {	"code":"400",	"data":{},	"description":"PC2755MH Incorrect status",	"errorCode":"",	"success":false}
-  Before this we have sent the 315 and received error:
  {
	"code":"400",
	"data":"",
	"description":"bin quantity locking! Please try again later",
	"errorCode":"",
	"success":false
}
- Now SSC want us to retirgger the in use and in transit for the asset for which return order is available
 - For PC2AG2Y4 we have no return order task created in SNOW
 - current status in SSC
   - PC2AG2Y4-In Use
   - PC2755MH- In Stock/Delivered’
   - Required status in SSC in-transit
1) Impacted records: 2
2) Additional info required from the reporter: N/A.
3) Solution steps:
	- Re-trigger the in-use and in transit for the PC2755MH
	  

1) Issue description: INC2024112002342: DaaS Production Issue Missing diskwipe attachment.
2) Reporter Name: jchan19
3) Impacted Table: sc_task
4) Account Name:   cisco
5) Analysis:   
	- The reporter has provided a report with condition stateNOT IN3,4,7,273^u_resolutions=Disk Wipe Completed^u_has_blancco_attachment=false
	- upon checking none of the asset are having blanco certificate
	- There are total 743 tasks and 741 assets with the return order task.
	- out of which 687 are in wiped state and we haven't received the disk wipe certificate and for 5 the substate is pending and for 49 the substate is empty
	- And the number of tasks is changing everytime.
	- 518 lenovo 169 apple
	- Blanco has responded for the ticket that diskwipe are available
1) Impacted records: 
2) Additional info required from the reporter: N/A.
3) Solution steps:
- Trigger the Blancco certificate flow for the records.
4) Issue description: DaaS Production Issue Missing Return Order Task - PF2XAKAJ
5) Reporter Name: zuzana
6) Impacted Table: sc_task
7) Account Name: cisco
8) Analysis:   
	- Cisco has opened a return REQ REQ0182416 // REQ5101726
	- Upon checking we could see that there is no return order task created.
	- Connected with to check and cisco confirmed task was created on their side and asked us to check the 20T5S1QS09 
9) Impacted records: 
10) Additional info required from the reporter: N/A.
11) Solution steps:



12) Issue description:
13) Reporter Name: 
14) Impacted Table:
15) Account Name:   
16) Analysis:   
	- 
17) Impacted records: 
18) Additional info required from the reporter: N/A.
19) Solution steps:




20) Issue description: INC2024120301606: DaaS Production Issue Cisco rejected COA for an order but COA Rejection Task was not created.
21) Reporter Name: iqueipo
22) Impacted Table: sc_task
23) Account Name:  cisco
24) Analysis:   
	- Assest FNJ7CVW056 was delivered on 11/17
	- It was rejected on 2 dec because of which cisco has not created the rejection task as per cisco 10 days COA window to reject.
	- Now cisco want us to create a rejection task manually and we've asked them for the payload.
25) Impacted records: 
26) Additional info required from the reporter: N/A.
27) Solution steps:




28) Issue description: INC2024112700173: investigate invalid PO generated in Task level
29) Reporter Name: Sedward
30) Impacted Table: sc_task
31) Account Name:  cisco
32) Analysis:   
	- Invalid PO updated in the task because no valid PO was present in the PO information table for Cisco US
	- Connected with the reporter and updated the valid PO in the PO information table.
	- For 2 task with canada account the PO number is present the PO information tabel but failed to be updated in the task because the customer used the entire state name "ONTARIO" instead of the two digit code "ON"
	- Now SNOW IT to update the valid PO on the sc_task.
33) Impacted records: 289
34) Additional info required from the reporter: N/A.
35) Solution steps:
   - Update the correct PO in the task level.
