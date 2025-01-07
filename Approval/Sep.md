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



1) Issue description: INC2024091300080 -  DaaS Production Issue Wrong delivery date in Cisco ServiceNow REQ4795645 | REQ0170669
2) Reporter Name:  zpodolska
3) Impacted Table:  alm_asset
4) Account Name:  Cisco
5) Analysis:  
   - As per our analysis due to some miscalculation in local date on OVP side they initially sent us the wrong date 2024-08-31 and the POD api got triggered with this data.
   - The customer confirmed that they received delivery on 2024-08-30 and the data has been corrected on OVP and SNOW but the change has not been reflected on Cisco side.
6) Impacted records:  1 record - PF53S7GA
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  DaaS | System Issue | OVP-Data Issues
12) Solution Steps: Re-trigger the POD api to Cisco with the correct delivery date.



1) Issue description:  INC2024091301243: Service Now not able Create bulk order Upload in service now
2) Reporter Name:  preddy5
3) Impacted Table:  Source table - u_pwcindia_bulk_order_process_ds 
				Targeted table - u_bulk_order_process_global
4) Account Name:  PWC
5) Analysis:  
-  As per our analysis the on-before transform script is ignoring the record due to the entity not matching with selected catalog entity.
6) Impacted records:  6 records - 
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: 
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:




PRICEWATERHOUSECOOPERS SERVICE DELIVERY CENTER (KOLKATA) PRIVATE LIMITED - a
i=use
PRICEWATERHOUSECOOPERS SERVICE DELIVERY CENTER (KOLKATA) PRIVATE LIMITED - cat

punith
PRICEWATERHOUSECOOPERS SERVICE DELIVERY CENTER (BANGALORE) PRIVATE LIMITED - cat
PricewaterhouseCoopers Ltd (India)PWC- HQ - 


Issue:
Service Now not able Create bulk order Upload in service now
Analysis:
In-correct Data: 
![[Pasted image 20240916174423.png]]
![[Pasted image 20240916174427.png]]


1) Issue description:  INC2024091600138: Need to change the Subscription end dates for Auto Extension
2) Reporter Name:  ka5
3) Impacted Table:  alm_asset
4) Account Name:  Cisco
5) Analysis:  
-  As per the current configurations the subscription end date in SNOW will be -1 day from LSP.
6) Impacted records:  61 records
7) Additional info required from the reporter: NA 
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  Extra service
12) Solution Steps: Change the Subscription end dates



1) Issue description:  INC2024091901422: SNOW The contract number (6900008785) Item price and Monthly price have a mismatch
2) Reporter Name:  kgangam
3) Impacted Table: # u_hardware_model_intermediate_price 
4) Account Name:  Other
5) Analysis:  
-  As per our analysis the reason for the mismatch is because the monthly price of bundle is calculated by adding up the monthly price of line items and the monthly price of line items is calculated by multiplying the item price with the exchange rate.
6) Impacted records:  3
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:

1) Issue description:  INC2024092002012: SNOW map the assets
2) Reporter Name:  svashisht
3) Impacted Table:  alm_asset
4) Account Name:  Other
5) Analysis:  
-  The reporter has initiated the copy task.  
- Need to remap the 274 assets (provided in the attached mail) to the new task SCTASK0519152, and the remaining assets to be mapped to the old task SCTASK0481012.
6) Impacted records:  517
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  DaaS | Manual Intervention | LOT-Copy Task Issues
12) Solution Steps: Need to remap the 274 assets (provided in the attached mail) to the new task SCTASK0519152, and the remaining assets to be mapped to the old task SCTASK0481012.
GM0MHV6W


1) Issue description:  INC2024092001050 DaaS Production Issue MYOB AU - Kindly assist to update the correct delivery date as 6 Sep -  SCTASK0514076
2) Reporter Name:  ytan7
3) Impacted Table:  alm_asset
4) Account Name:  MYOB  
5) Analysis:  
-  The asset delivery date has wrongly been updated as 2024-06-09 via Third party asset upload.
- Now they want to update the delivery date as 2024-09-06
6) Impacted records:  1
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  Error | DaaS | Delivery date Issue
12) Solution Steps: Need to change the delivery date to 6 Sep

1) Issue description:  INC2024092002012 SNOW map the assets
2) Reporter Name:  svashisht
3) Impacted Table:  alm_asset
4) Account Name:  Other
5) Analysis:  
-  The reporter has initiated the copy task.
-  task contains 518 assets, but the customer want to bill 274 assets only. Need to remap the remaining assets to the old SCTASK0481012.
- Among 274 asset provided, 79 are already aligned with SCTASK0519152 and we need to remap 195 assets to SCTASK0519152.
- Need to move the remaining assets to old SCTASK0481012
6) Impacted records:  195
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:   DaaS | Manual Intervention | LOT-Copy Task Issues
12) Solution Steps: Need to remap 195 assets to SCTASK0519152 and move the remaining assets to old SCTASK0481012


1) Issue description:  INC2024090500288: DaaS Production Issue Missing shipment and POD data in Cisco ServiceNow
2) Reporter Name:  zpodolska
3) Impacted Table:  alm_asset
4) Account Name:  Cisco
5) Analysis:  
-  As per our analysis, OVP has sent us Shipped status initially and then sent us the 'Shipment date' due to which when the shipment API was triggered the Shipment date was empty due to which cisco rejected the Shipment API.
- After, OVP has sent us the incorrect delivery date.
- The reporter has confirmed that the correct delivery date is August 28th. The correct delivery date has been updated in OVP.
- The correct delivery date has to be updated in SNOW.
6) Impacted records: 1
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  
11) Issue Type:  
12) Solution Steps:
   step 1: Update the correct delivery date in SNOW system.
   step 2: retrigger the Shipment and POD api.




INC2024092301846:

![[Pasted image 20240924232520.png]]

According to this incident INC2024010400079 the asset has been mapped to task SCTASK0438843 the asset has been accepted and moved to in use ( **GM02D9BE**)

INC2024080900419 as per this ITSM the serial number was mapped to SCTASK0438843.

Analysis:

The asset was in In stock available and it was mapped to SCTASK0509256 and CSC attached GM02D9CV and deleted the **GM02D9BE** from SCTASK0509256 and processed this to SSC. Now need to align the **GM02D9BE** back to SCTASK0438843.


On ticket:

According to this incident INC2024010400079 the asset has been mapped to task SCTASK0438843 the asset has been accepted and moved to in use ( **GM02D9BE**)

INC2024080900419 as per this ITSM the serial number was mapped to SCTASK0438843.

The asset was in In stock available and it was mapped to SCTASK0509256 and CSC attached GM02D9CV and deleted the **GM02D9BE** from SCTASK0509256 and processed this to SSC. Now need to align the **GM02D9BE** to SCTASK0438843.




1) Issue description:  INC2024092301846: DaaS Production Issue PWC AU - GM02D9BE Pls check why SN was fulfilled via REQ0148611 back in 4th Jan 2024. 2. update SN back to correct Task REQ0148611 / SCTASK0438843
2) Reporter Name:  ytan7
3) Impacted Table:  alm_asset
4) Account Name:  PWC AU
5) Analysis:  
- The GM02D9BE asset has been picked up in the SCTASK0509256 because the State of the asset is "**In Stock - Available**".
- the M2M asset "**GM02D9BE**" was deleted by the user "lyap2" from SCTASK0509256.
6) Impacted records:  1
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  DaaS | Manual Intervention | Customer/CSC-Asset Management
12) Solution Steps:
- To recover the deleted record GM02D9BE from the Deleted records  
-   And remap the asset GM02D9BE back to the SCTASK0438843 as per the reporter's request.
Could you explain why user "lyap2" removed the M2M asset "GM02D9BE" from SCTASK0509256?



This is a history record and C05 is not tirggered for this asset, 
Latter when COI order is raised 315 didn't got triggered and when it  got returned 313 has been triggered which resulted in an error from SSC.
SCTASK0086333 


1) Issue description:  INC2024092501507: SNOW Unable to book in SSC - PF2PJKBF
2) Reporter Name:  pquirk
3) Impacted Table:  alm_asset
4) Account Name:  Grant Thornton
5) Analysis:  
-  As per the user the state of the asset in SSC is incorrect, it should be in "in transit" but it is in "In stock Delivered".
- In transit 313 has been triggered from SNOW and Received an error "in correct status".
- Upon checking with SSC the issue is the asset needs to be in In use before it can be changed to In transit.
- SSC has instructed us to trigger the in use state and then in transit.
- In use C05 state has not been triggered from SNOW to SSC since it is a history record.
6) Impacted records:  1
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  
12) Solution Steps: 
    - Need to trigger In use state to SSC and then trigger In transit.




1) Issue description:  INC2024092700703: remove Subscription Order # for below mentioned Task because the Billing start date
2) Reporter Name:  katla
3) Impacted Table:  sc_task
4) Account Name:  Cisco
5) Analysis:  
-  As per the reporter, Billing start date, Subscription start date is picked incorrectly and Tranche ID also not correct in LSP and they have canceled the SO #.
- Hence, they want us to remove Subscription Order for the mentioned task.
6) Impacted records:  4
7) Additional info required from the reporter: NA  
8) Proposed temporary solution: Same as Solution steps  
9) Permanent Solution: NA  
10) Cause of the issue (RCA):  Requests-Special biz scenario support
11) Issue Type:  
12) Solution Steps:
	 - Need to remove Subscription Order for the mentioned task.



1) Issue description: DaaS Production Issue Red Cross - SN PF3KERJL was picked up by system, & pls help to assign back to SCTASK0426338

2) Reporter Name: ytan7

3) Impacted Table: Deleted records

4) Account Name: Red Cross Australia

5) Analysis:

- the M2M asset "**PF3KERJL**" was deleted by the user "**elee35**" from **SCTASK0426338**.

- The PF3KERJL asset has been picked up in the SCTASK0513969 because the State of the asset is "**In Stock - Available**".

6) Impacted records: 1 deleted record - PF3KERJL

7) Additional info required from the reporter: NA

8) Proposed temporary solution: Same as Solution steps

9) Permanent Solution: NA

10) Cause of the issue (RCA): Requests-Special biz scenario support

11) Issue Type: DaaS | Manual Intervention | Customer/CSC-Asset Management

12) Solution Steps:

- To recover the deleted record "PF3KERJL" from the Deleted records

- And remap the asset "PF3KERJL" back to the SCTASK0426338 as per the reporter's request.

- Link: https://lenovoau.service-now.com/sys_audit_delete_list.do?sysparm_query=display_valueLIKEPF3KERJL%20&sysparm_first_row=1&sysparm_view=&sysparm_choice_query_raw=&sysparm_list_header_search=true

- Deleted by: elee35
  
  
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
      
      
The asset came to us in delivered state hence SHipment and pod br got triggered.
Due to that the task was move to pend for bill


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


