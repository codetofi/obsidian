### **Router**:

- A router is responsible for **routing** traffic between different networks or subnets.

### **Switch**:

- A switch operates at the **data link layer (Layer 2)** of the OSI model and is used to **connect devices within the same subnet**.
- It uses **MAC addresses** to forward data to the correct device within a subnet.

### **How IP Ranges Work in Discovery**

1. **Defining the IP Range:**
    
    - The network administrator specifies the range of IP addresses to be scanned.
    - Example: A range like `192.168.1.1 - 192.168.1.255` includes all 255 possible devices within the **192.168.1.x** subnet.
2. **What Happens During the Scan:**
    
    - ServiceNow's **MID Server** sends requests to each IP address in the defined range.
    - If a device responds (e.g., a server or router), Discovery proceeds to identify it and gather details.
3. **Adjusting the Range:**
    
    - You can define broader or narrower ranges depending on the scope of your infrastructure.
        - **Broad Range**: `192.168.0.1 - 192.168.255.255` covers multiple subnets.
        - **Narrow Range**: `192.168.1.1 - 192.168.1.50` focuses only on the first 50 devices.
	
	
	#### **Real-World Example**
	
	
	Imagine a company has two office locations:
	
	- **Office A** network: `192.168.1.1 - 192.168.1.255`
	- **Office B** network: `10.0.0.1 - 10.0.0.255`
	
	The administrator can configure separate Discovery schedules for each office using the respective IP ranges. When Discovery runs:
	
	1. For **Office A**, ServiceNow scans all devices within `192.168.1.x`.
	2. For **Office B**, ServiceNow scans all devices within `10.0.0.x`.



### **Probe , MID server, Sensors**
**Sensors are specialized scripts or modules that process raw data collected by probes and convert it into structured, meaningful information that can be used to populate the Configuration Management Database (CMDB).**

**Here's a breakdown of the process mentioned in your example:**

#### **1. Probe**
**The probe is the component that gathers raw data from the target system. It sends out requests to various devices or servers and collects data based on predefined patterns (e.g., HTTP, SSH, WMI).**
**This raw data can include information like IP addresses, hostnames, operating system details, hardware specs, installed software, and more.**
#### **2. MID Server**
**The MID (Management, Instrumentation, and Discovery) Server is a bridge between ServiceNow and your network. It is responsible for collecting and forwarding the raw data from the probe to ServiceNow, securely and without exposing sensitive information directly to the cloud.**

##### **Role of the MID Server:**
**The MID Server acts as the bridge between your on-premises infrastructure and ServiceNow’s cloud platform.**
**It runs probes (scripts that gather raw data from the target systems), but it does not contain sensors.**
**The MID Server forwards the collected raw data to ServiceNow.**
#### **3. Sensors**
**Sensors are components within the ServiceNow Discovery module that take the raw data received from the probe and process it into structured, usable information.**
**They transform this unprocessed data into CI (Configuration Item) attributes, such as hostnames, IP addresses, software versions, hardware details, and more.**

##### **Role of Sensors:**
**Sensors are part of ServiceNow Discovery, which is hosted on the ServiceNow platform (cloud).**
**After the MID Server sends the raw data to ServiceNow, the sensors process that data.**
**Sensors are responsible for interpreting and structuring the raw data into usable Configuration Item (CI) records, which are then stored in the Configuration Management Database (CMDB).**



**Example of Sensor Functionality:**
**Let’s break down your example:**

**Raw Data from the Probe:**

**yaml**
**Copy code**
**IP address: 192.168.1.100**  
**Hostname: webserver01**  
**OS: Ubuntu 22.04**  
**CPU: 4 cores**  
**RAM: 16GB**  
**Software: Apache 2.4, MySQL 8.0**
**Sensor's Role:**

**A sensor will process this raw data to create structured Configuration Item (CI) records in the ServiceNow CMDB.**
**The sensor will recognize specific attributes such as:**
**Hostname = webserver01**
**IP address = 192.168.1.100**
**Operating System = Ubuntu 22.04**
**CPU cores = 4 cores**
**RAM = 16GB**
**Installed Software = Apache 2.4, MySQL 8.0**
**It organizes and structures the data, then sends it to ServiceNow, where it is used to create or update Configuration Items (CIs).**

### **How CMDB became "Service aware" (Veeran uuruvana tharunam)**

**Service Mapping takes the existing CIs in the CMDB (like the web servers, application servers, databases, etc.) and visually shows how they are connected to each other to form a complete service. For example, in the "Online Shopping Service," you will see how the web server connects to the application server, which then connects to the database server, and how all of these work together to provide the e-commerce functionality.**

#### **Making the CMDB "service-aware":**
**By adding these relationships and service maps, the CMDB becomes more than just a collection of individual CIs. It becomes aware of the service itself — meaning, instead of only knowing that a server exists, it now knows that this server is part of a specific service and how it contributes to that service. This "service-aware" feature is important because:**

##### **Dependencies: It can track which other CIs rely on a particular CI (for example, if the web server goes down, it will impact the e-commerce service).**
##### **Impact analysis: If there’s an issue in one part of the service, you can understand how it affects other parts of the service.**
##### **Troubleshooting: You can trace issues more easily because the CMDB knows the relationships between CIs.**

#### **Real-Time Example:**
**Imagine you're running a cloud-based email service. The service includes various components like:**

**Mail Servers (CIs)**
**SMTP Servers (CIs)**
**Database Servers (CIs)**
**Load Balancers (CIs)**
**Web Servers (CIs)**
**In the CMDB, you may have individual records for each of these components (CIs). However, until Service Mapping is applied, the CMDB doesn’t "know" that these components are part of the email service.**

**When you apply Service Mapping, it creates a map that shows the relationship between these CIs and how they work together to provide the email service. For instance:**

**Web servers depend on mail servers for sending emails.**
**Database servers store user data, which the email service uses.**
**Load balancers distribute traffic across web servers.**
**Now, the CMDB becomes "service-aware" because it understands the dependencies between these CIs. If a mail server goes down, ServiceNow can notify you that it will impact the entire email service.**



### **CSDM**

**The Common Service Data Model (CSDM) is a set of guidelines for organizing data in ServiceNow's CMDB (Configuration Management Database).**

**Think of it as a map that tells you how to connect all the pieces of your IT environment (like applications, services, users, and infrastructure) in a standardized way.**

**Why is CSDM important?**
**Standardization: It ensures everyone follows the same rules for structuring data.**
**Service Visibility: It helps you understand how IT services work and what they depend on.**
**Reporting and Decision-Making: With properly organized data, it’s easier to generate reports and make decisions.**
**CSDM Simplified:**
**Imagine running a restaurant:**

**Foundation: The restaurant details (location, staff, equipment).**
**Design: The menu and recipes (what you offer and how you deliver it).**
**Manage Technical Services: The kitchen operations (tools and processes to prepare food).**
**Sell/Consume: The dining experience for customers (services they enjoy).**
**CSDM is like organizing all this information clearly so your restaurant runs smoothly. For ServiceNow, it helps manage IT services effectively.**

**Let me know if you’d like a deeper breakdown of any specific part!**