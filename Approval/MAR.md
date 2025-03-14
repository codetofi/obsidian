
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

1) Issue description: DaaS Production Issue CISCO - IN || Snow IT to replace WUR unit with replacement unit and ensure billing following original **WUR assets**
2) Reporter Name: Salmi
3) Impacted Table: alm_asset
4) Account Name:   Cisco
5) Analysis:   
	-  Cisco has reported PF3J36KW / REQ0090796 / REQ1645037 as DOA. SN# PF5F0WTF (X1 carbon Gen. 12) delivered under REQ0173444 / G000204942
	- LOT has performed copy task on REQ0090796 / REQ1645037 and model mapping. Old task SCTASK0290299 New task(copy task) - SCTASK0623331
	- Now the ask here is to map 19 devices back to the old task SCTASK0290299.
6) Impacted records: 
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- Map 19 devices back to the old task SCTASK0290299.

For task,
SCTASK0632771
SCTASK0632768
We're receiving the following error
<html>
<head><title>504 Gateway Time-out</title></head>
<body>
<center><h1>504 Gateway Time-out</h1></center>
<hr><center>nginx</center>
</body>
</html>

For SCTASK0632769 - ECC order number is not generated.
For SCTASK0632767- <am:fault xmlns:am="http://wso2.org/apimanager"><am:code>303001</am:code><am:type>Status report</am:type><am:message>Runtime Error</am:message><am:description>Currently , Address endpoint : [ Name : ServiceNowOrder--vv1.0_APIproductionEndpoint ] [ State : SUSPENDED ]</am:description></am:fault>
For SCTASK0632766 - "[The TaskNo has already existed with orderNumber:25030301485]"


1) Issue description: INC2025030300878: DaaS Production Issue Failed Post RR Order
2) Reporter Name: Aliff
3) Impacted Table: sc_task
4) Account Name:   Shangri-La Malaysia
5) Analysis:   
	- 
6) Impacted records: 
7) Additional info required from the reporter: N/A.
8) Solution steps:
- 


INC2025030402636 - DaaS Production Issue Please change status of Cisco Apple returns to In Stock

Reason as per the reporter:
These devices were picked up by AFS and never received into a Lenovo CFS. Therefore, we have to manually update the status in order for the device to be deregistered from Apple ABM and allow AFS to complete diskwipe and the condition report.

Analysis:
- Upon investigating we could see that we have in total of 1922 SN in the provided file, out of which we have 1057 are in "In stock" state, 3 are in "In use" and One is in "missing" state and rest 931 are in "In Transit" state.
- For the 3 SN in "in use" two don't have return order task and one has return order task processed to SSC but received SN does not exist error as we have not triggered C05 as this is a history record 2021.
  Solution: We're done wit the execution for the SN with return order number and now it has been moved to in transit.
- For the 1 SN in Missing state it has been updated by LOT team.
- For the SN 931 SN +1 SN after SNow IT work around are in "In transit" SSC has to send us the "In stock" state as the "In stock" state is flow from SSC to SNow.


As per our analysis for the provided SN list,

Upon investigating we could see that we have in total of 1922 SN in the provided file, out of which we have 1057 are in "In stock" state, 22 are in "In use" and One is in "missing" state and rest 932 are in "In Transit" state.

1) 1057 are already in "In transit" state so there is no action needed from SNow IT to update to In stock.
2) For the 2 SN that are in In use state as there is no return order task attached to these SN.
3) For the 1 SN in Missing state it has been by LOT team.
4) For the rest of the 932 SN in "In Transit" state SSC has to send us the "In stock" state as the "In stock" state is flow from SSC to SNow.
   
This ITSM needs to be transferred to SSC team to check on this.


Analysis:
 Upon investigating we could see that we have in total of 1922 SN in the provided file, out of which we have 1057 are in "In stock" state, 3 are in "In use" and One is in "missing" state and rest 931 are in "In Transit" state.
 
1) 1057 are already in "In transit" state so there is no action needed from SNow IT to update to In stock.
   Solution: No action required.
2) For the 3 SN in "in use" two of them don't have return order task and one has return order task.
    Solution: We're done wit the execution for one SN with return order number and now it has been moved to in transit.
3) For the 1 SN in Missing state it has been by LOT team.
	 
4) For the SN 931 SN +1 SN (after SNow IT work around) are in "In Transit" state and SSC has to send us the "In stock" state as the "In stock" state is flow from SSC to SNow.
      Solution: No action required from SNow IT, SSC to check on this.
This ITSM needs to be transferred to SSC team to check on this.



1) Issue description: INC2025030302856: Service now Split and reassign SN - Mexichem Servicios Administrativos
2) Reporter Name: ahernandez90
3) Impacted Table: alm_asset
4) Account Name:   MEXICHEM SERVICIOS ADMINISTRATIVOS	
5) Analysis:   
	- The ask here is to map the 67 SN provided in the ITSM to the task  SCTASK0566815 and SCTASK0566785 mentioned in the ITSM.
	- As per the reporter the are going to invoice 33 SN in March. These 33 assets are distributed between SCTASK0566815 and SCTASK0566785.
	- Now they want us to map 33 SN to SCTASK0566785 and rest to the other task.
6) Impacted records: 67
7) Additional info required from the reporter: N/A.
8) Solution steps:
	- Map the SN as per the request

REQ5539994 - 4e3b750d83d69210301ec988beaad30b
REQ5550923 - 090fa2acc357d210cc5e8b0ad001310f
REQ5546236 - 4e3b750d83d69210301ec988beaad30b
REQ5545738 - 090fa2acc357d210cc5e8b0ad001310f
REQ5545712 - 090fa2acc357d210cc5e8b0ad001310f
REQ5562584 - 901f26acc357d210cc5e8b0ad001310c
REQ5560226 - 4e3b750d83d69210301ec988beaad30b
REQ5575902 - 901f26acc357d210cc5e8b0ad001310c

https://lenovoau.service-now.com/now/nav/ui/classic/params/target/sc_cat_item_list.do%3Fsysparm_query%3Dsys_idIN4e3b750d83d69210301ec988beaad30b%252C090fa2acc357d210cc5e8b0ad001310f%252C901f26acc357d210cc5e8b0ad001310c%252C%26sysparm_first_row%3D1%26sysparm_view%3D



1) Issue description: DaaS Production Issue CISCO - JP || MSCT to DND asset & reupload with correct details: REQ0195663 / REQ0195664 / REQ0195665
2) Reporter Name: Salmi
3) Impacted Table: alm_asset
4) Account Name:    Cisco
5) Analysis:   
	- The ask her is to update the shipment date as 2025-02-10 for the three SN as these were uploaded with this date.
6) Impacted records: 
7) Additional info required from the reporter: N/A.
8) Solution steps:
 -  


as

1) Issue description: DaaS Production Issue KPMG - NZ || MSCT IT to swap asset in SNow & LSP to swap asset in LSP (WUR) : REQ0109914 / REQ0081698 / SCTASK0407754 / SCTASK0407754;
2) Reporter Name: cli22
3) Impacted Table: alm_asset
4) Account Name:    Cisco
5) Analysis:   
	- The ask here is to move the asset# PF5AAX5E into #SCTASK0407554 from #SCTASK0407754
	- Reason: MSCT mistakenly uploaded in #**SCTASK0407754**
	- Upon checking SCTASK0407754 - REQ0109914
	   SCTASK0407554 - REQ0081698
	   task are under different requests.
	
6) Impacted records: 1
7) Additional info required from the reporter: N/A.
8) Solution steps:


csA

1) Issue description: DaaS Production Issue CISCO - IN || Snow IT to replace WUR unit with replacement unit and ensure billing following original WUR assets
2) Reporter Name: Salmi
3) Impacted Table: alm_asset
4) Account Name:   cisco
5) Analysis:   
	- MSCT has uploaded the SN on 06-03-2025 now the ask here is to update the install date as per the actual delivery date.
6) Impacted records: 1
7) Additional info required from the reporter: N/A.
8) Solution steps:
-  update the install date as per the actual delivery date.


 
	 G000233841 - NO SN
	 G000233850 - PF5C3W0V
	 G000233846 - PF5BZSRH
	 
	 Current SN in ServiceNow with the ECC No.
	  G000233846 - PF5C0WH8
	  G000233850 - PF5BZSRH
	  G000233841 - PF5C3W0V

Hi Eswar Kumar Palla

Below ticket is for approval

1) Issue description: DaaS Production Issue CISCO - IN || Snow IT to replace WUR unit with replacement unit and ensure billing following original WUR assets  
2) Reporter Name: Salmi  
3) Impacted Table: alm_asset  
4) Account Name:   cisco  
5) Analysis:     
  - MSCT has uploaded the SN PF5F0WTF on 06-03-2025.
  - It is the replacement SN for PF3J36KW (WUR).
  - Now the ask here is to update the install date as 2022-08-07 to follow the original billing that is the install date of the DOA SN PF3J36KW 
1) Impacted records: 1  
2) Additional info required from the reporter: N/A.  
3) Solution steps:  
-  update the install date as per the ask.


vd



1) Issue description:  INC2025031001856 : DaaS Production Issue CAPEX Order not flipped to closed complete after delivery
2) Reporter Name:  qtan1
3) Impacted Table: sc_task
4) Account Name:  Valvoline
5) Analysis:  
-  The asset is created in delivered state and hence Valvoline - Shipment and POD API BR got triggered.
- Due to this the task was moved to pending for billing.
1) Impacted records:  1
2) Additional info required from the reporter: NA  
3) Proposed temporary solution: Same as Solution steps  
4) Permanent Solution: DS-13749
5) Cause of the issue (RCA):  Requests-Special biz scenario support
6) Issue Type:  
7) Solution Steps:
        -  Move the task to closed complete state.


2022-08-07
|   |
|---|
|2022-07-08|


{"u_ritem_number":null,"u_comments":"Lenovo Update: Absolute request has been processed for serial number PF2M0FQ3 , pending for fulfillment from Absolute."} praveen lock

{"u_ritem_number":"RITM0128624","u_comments":"Lenovo Update: Absolute request has been processed for serial number , pending for fulfillment from Absolute."} - me


RED cross Payload

SCTASK0290723 - Shipment and POD payload

REQ0204988 -  comments  - REQ0204980

SCTASK0642325 - ETA

PF3FRMBM only one rejected asset 

NO contract rest message method, PF3FQEPJ this one contract api executed but to multiplex.

REQ0089559 - Lost stolen

SCTASK0372428 - absolute unlock 


