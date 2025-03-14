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



### **Probe , MID server, Sensors, Pattern, additional probes**
**Sensors are specialized scripts or modules that process raw data collected by probes and convert it into structured, meaningful information that can be used to populate the Configuration Management Database (CMDB).**

**Here's a breakdown of the process mentioned in your example:**
![[Pasted image 20250209001058.png]]
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

#### **Here’s how the process works:**

Discovery Starts:

The MID Server runs Discovery on the organization’s internal network. It begins by gathering a list of IP addresses in the network or by scanning a specific IP range.
Probe Execution:

The MID Server sends out a probe to each device (like a server, workstation, or printer) in the network to collect basic information.
For example, the probe may gather the IP address, hostname, MAC address, and open ports of a server.
Identifying the Type of CI:

Based on the data collected by the probe (e.g., the IP address, hostname, open ports, and other details), ServiceNow Discovery tries to determine the type of device (e.g., server, workstation, printer).
If the device is identified as a server, for example, Discovery will use a set of patterns designed to gather additional details relevant to a server.

#### What Are Patterns?

Patterns in ServiceNow Discovery are predefined logic or templates that define how to collect additional information based on the type of Configuration Item (CI).
Once Discovery identifies the type of CI (e.g., a server, network device, or printer), it uses these patterns to gather more specific details about the CI.
Example of Patterns:

Server Pattern: If the system identified is a server, the pattern for servers might include steps to:
Discover the operating system (e.g., Windows, Linux)
Identify the installed software (e.g., Apache, MySQL)
Gather hardware details (e.g., CPU, memory, disk space)
Collect network configuration (e.g., IP address, DNS settings)
Network Device Pattern: If the system is a network switch, the pattern may include:
Discovering the model and manufacturer
Identifying ports and their usage
Collecting firmware and configuration details
These patterns allow Discovery to adapt dynamically to different types of devices and systems.

#### What is an Additional Probe?

Additional probes refer to specific probes that are launched once the initial probe runs and the type of CI is identified.
These probes are used to gather further specific data based on the type of device or system being discovered.
Example of an Additional Probe:

Suppose Discovery identifies a server. After identifying the server, the MID Server will run an additional probe (for example, an SSH probe or WMI probe) to gather further details like:
OS version (e.g., Ubuntu 20.04 or Windows Server 2019)
CPU details (e.g., number of cores, architecture)
Memory and storage configuration (e.g., RAM size, disk partitions)
Similarly, if the device is a printer, an additional probe might be launched to gather details like:
Model and serial number
Installed toner levels
Network settings
These additional probes are launched only when they are needed, depending on the type of CI being discovered.

Summary of Key Components:

**Probes: Scripts that gather basic data from devices (e.g., IP address, hostname, open ports). They run initially to gather raw data.**
**Patterns: Templates or logic that determine how to collect additional information based on the CI type (e.g., server, network device). They help structure the discovery process for different kinds of systems.**
**Additional Probes: Probes launched after the initial probe to gather further specific details based on the type of device being discovered (e.g., server, printer, etc.).**
**Putting It All Together:**
**Discovery starts by sending a basic probe to a device.**
**The probe gathers basic information (like the IP address or hostname).**
**ServiceNow identifies the type of device (e.g., server, printer).**
**Based on this, Discovery uses a pattern to determine what additional data is needed.**
**Additional probes are launched based on the pattern (e.g., gather OS details for a server, or model and serial number for a printer).**
**The structured data is then sent to ServiceNow, where it is processed by Sensors and stored in the CMDB as a Configuration Item (CI).**

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

### **ServiceGraph Connectors and how it is different from Discovery** 
#### **What Are Service Graph Connectors?**

Service Graph Connectors are pre-built integrations provided by ServiceNow to **seamlessly import and map data from third-party systems into the ServiceNow CMDB (Configuration Management Database)**.  
They are part of the **Service Graph Framework**, which ensures that data is clean, consistent, and well-structured when brought into the CMDB.

#### **Why Do We Need Service Graph Connectors?**

In modern organizations, IT infrastructure and services are managed across multiple tools. Examples:

- Virtual machines managed via VMware.
- Cloud resources managed via AWS or Azure.
- Networking equipment tracked via Cisco tools.

If these tools work in silos, the CMDB in ServiceNow will lack the complete picture. Service Graph Connectors bring **unified, reliable data** from these tools into the CMDB, ensuring:

1. **Data Accuracy**: Prevents duplicates, missing relationships, and inconsistencies.
2. **Automation**: Eliminates the need for manual imports.
3. **Relationship Mapping**: Automatically maps relationships between CIs (e.g., linking a virtual machine to its host).

---

#### **How Service Graph Connectors Work**

##### 1. **Connection to Third-Party Tools**

Each Service Graph Connector is designed for a specific tool or system. For example:

- **VMware vCenter Connector**: Connects to vCenter to bring data about virtual machines, hosts, and clusters.
- **AWS Connector**: Pulls in data about EC2 instances, S3 buckets, RDS databases, etc.

##### 2. **Data Ingestion**

The connector fetches CI data (e.g., servers, storage devices, software) and sends it to the CMDB.

##### 3. **Data Mapping and Transformation**

Before importing data into the CMDB, the connector ensures:

- **Mapping**: Maps third-party data fields to the CMDB schema.
    - Example: External tool's "VM Name" is mapped to CMDB's "Name" field for the VM CI.
- **Deduplication**: Ensures no duplicate records are created.
- **Validation**: Checks for data quality issues.

##### 4. **Relationship Mapping**

The connector maps relationships between CIs. For example:

- A virtual machine (VM) is hosted on a physical server.
- The connector maps the VM to its host and reflects this in the CMDB.

---

#### **Example Use Case: VMware vCenter Service Graph Connector**

##### **Scenario**

An organization uses VMware vCenter to manage its virtualized infrastructure. They want this information available in the CMDB for better visibility and management.

##### **Steps**

1. **Install the Connector**: The VMware vCenter Service Graph Connector is installed from the ServiceNow Store.
2. **Configuration**:
    - Provide vCenter API credentials.
    - Specify the data to import (e.g., virtual machines, hosts, clusters).
3. **Data Import**:
    - The connector retrieves data about all virtual machines (VMs), hosts, and their configurations.
    - Example:
        - VM:
            - Name: `VM01`
            - Hostname: `host01`
            - IP Address: `192.168.1.10`
            - OS: `Ubuntu`
        - Host:
            - Name: `host01`
            - CPU: `16 cores`
            - RAM: `64GB`
    - The relationship between VM01 and host01 is also captured.
4. **CMDB Update**:
    - This data is validated, mapped, and imported into the CMDB.
    - If a VM is deleted in vCenter, the CMDB record is marked as decommissioned.

---

##### **Key Features of Service Graph Connectors**

1. **Out-of-the-Box Support**:
    
    - No need for custom scripts or complex integrations.
    - ServiceNow provides connectors for popular platforms (AWS, Azure, VMware, Cisco, etc.).
2. **Automated Updates**:
    
    - Keeps the CMDB synchronized with external systems in near real-time.
3. **Relationship Awareness**:
    
    - Captures and maps relationships between components (e.g., VMs, storage, networks).
4. **Data Quality Enforcement**:
    
    - Ensures that the CMDB remains accurate and reliable.

---

#### **Supported Platforms**

Some examples of tools/platforms with Service Graph Connectors:

- **Cloud Platforms**: AWS, Azure, Google Cloud.
- **Virtualization**: VMware vCenter, Hyper-V.
- **Networking**: Cisco ACI, F5 Load Balancers.
- **ITSM and Monitoring**: SolarWinds, Splunk.

---






### **SG connectors VS Discovery**
#### **1. Service Graph Connectors**

**Purpose**:

- **Prebuilt integrations** to bring data into the CMDB from **specific third-party tools or services**.

**Key Characteristics**:

- **Targeted Data Integration**:
    - Designed for third-party tools like VMware vCenter, AWS, Azure, or other cloud/on-premise IT management tools.
    - They leverage APIs or SDKs provided by the third-party tools.
- **Agentless**:
    - No probes or sensors; they directly integrate with external systems via APIs.
- **Focus on Data Accuracy**:
    - Enforce **Service Graph data model standards** (ensuring the data aligns perfectly with the CMDB structure).
- **Simplified Setup**:
    - Service Graph Connectors come with predefined rules for specific tools, so you don’t have to customize much.

**Example Use Case**:

- Your organization uses VMware vCenter to manage virtual machines. A **Service Graph Connector** for VMware retrieves details about VMs, their hosts, and relationships directly from vCenter APIs.
- It ensures this data is formatted and structured correctly for the CMDB without needing custom probes or sensors.

---

#### **2. ServiceNow Discovery**

**Purpose**:

- **Generic scanning tool** to detect and identify all IT assets in your infrastructure, whether physical, virtual, or cloud-based.

**Key Characteristics**:

- **Broad Scope**:
    - Capable of discovering devices, servers, applications, cloud resources, databases, and networking equipment.
    - Can discover infrastructure **even if you don’t use third-party tools** (e.g., unmanaged devices).
- **Probes, Sensors, and Patterns**:
    - Uses probes and sensors to scan and collect data.
    - Patterns analyze the collected data to identify CIs and relationships.
- **Requires MID Server**:
    - Discovery relies on a MID Server to interact with the internal network and collect data.
- **Dynamic Detection**:
    - Continuously scans your network to discover changes, ensuring CMDB stays up-to-date.

**Example Use Case**:

- Your network has physical servers, routers, and switches that aren’t managed by any specific tool like VMware. **Discovery** scans the network, identifies these devices, and populates them in the CMDB.

---

#### **Differences Between Service Graph Connectors and Discovery**

|**Aspect**|**Service Graph Connectors**|**ServiceNow Discovery**|
|---|---|---|
|**Target Source**|Specific third-party tools (e.g., VMware, AWS, Azure).|Entire IT infrastructure (physical, virtual, cloud).|
|**Implementation**|Prebuilt integrations with APIs/SDKs of specific tools.|Generic discovery using probes, sensors, and patterns.|
|**Agentless/Agent-Based**|Fully agentless, uses APIs.|Uses MID Server for scanning and discovery.|
|**Scope**|Limited to data from third-party tools.|Broader scope; discovers unmanaged devices and custom setups.|
|**Use Case**|Bring data from tools already managing your infrastructure.|Discover assets not tracked by any tool and maintain updates.|
|**Data Quality**|Enforces Service Graph data model for better CMDB data structure.|Custom patterns are required for some unique CIs or setups.|
|**Setup Complexity**|Easy to set up with predefined connectors.|Requires configuration and patterns for specific use cases.|

---

#### **How They Complement Each Other**

- **Service Graph Connectors**: Best for environments where IT infrastructure is already managed by third-party tools. They streamline data integration from those tools into the CMDB.
- **ServiceNow Discovery**: Best for environments with unmanaged devices, hybrid setups, or when you need a complete infrastructure overview, including devices/tools that don’t have connectors.

**Together**:

- Organizations often use **both tools** to unify all their data in the CMDB. For example:
    - Use a Service Graph Connector to get VM details from VMware vCenter.
    - Use Discovery to identify unmanaged networking devices or physical servers.

---

#### **Real-World Analogy**

Imagine your CMDB as a **library catalog**:

1. **Service Graph Connectors** are like partnerships with major publishers (e.g., VMware, AWS, Azure) who send you complete books (structured CI data).
2. **ServiceNow Discovery** is like sending librarians to search the library shelves (your IT network) and manually catalog any books (devices) they find, even if they’re not from a known publisher.


### **CMDB Approach and Architecture**



![[Pasted image 20250109195512.png]]
![[Pasted image 20250110125126.png]]
### **Overview of the Device Discovery Process (MID server) and how ports help in this

#### Probing the Device:

The MID Server sends a probe to the IP addresses defined in the range.
A device at the given IP responds to the probe, indicating it exists and is reachable.

Initial Identification:

The response from the device includes basic data, such as network information.
This basic information helps Discovery identify whether the device is active and can communicate.

Classification:

ServiceNow uses classification patterns to determine the type of device (e.g., server, laptop, printer).
This step may involve analyzing:
Open ports.
Protocols (e.g., SSH, WMI, SNMP).
Device-specific responses.
Deep Discovery:

After identifying the device type, Discovery runs more targeted probes to gather detailed information.

#### Example:
For a server, it may check the OS, installed software, and running applications.
How Does Port Scanning Fit In?
When a device responds to the initial probe, Discovery often uses port information to classify and identify it further. Here’s how it works:

Initial Response:

The device responds to a basic probe. For example:
It sends information like an IP, hostname, or basic protocol data.
Port Scanning:

Discovery checks for open ports on the device.
Ports are used to identify what services or applications are running.
Example:
Port 22 indicates an SSH service (likely a Linux/Unix server).
Port 3389 indicates RDP (likely a Windows server).
SNMP ports (161, 162) are common for printers and network devices.
Using Ports for Classification:

Based on the open ports, Discovery applies classification patterns:
If Port 22 is open, it triggers an SSH-based classification pattern.
If Port 3389 is open, it triggers a WMI or Windows classification pattern.
If SNMP ports are open, it applies network device or printer classification patterns.
Targeted Probing:

Once the device is classified, additional probes gather more detailed data:
For a Linux server: Probes collect OS version, RAM, CPU, etc., via SSH.
For a Windows server: Probes collect similar data via WMI.
For printers or network devices: SNMP probes gather model, configuration, and performance data.
Why Not Identify Device Type First Before Port Scanning?
Discovery uses ports as a clue to quickly determine the device type because:

Efficiency:
Ports provide a quick and reliable way to infer what type of device it might be.
Protocol-Driven Discovery:
The protocols/services running on those ports guide the classification process.
Clarified Example: Discovery of a Device
Let’s apply this process to an example:

#### Scenario:
The MID Server probes an IP address, 192.168.1.100.
The device responds, confirming it is reachable.
Steps:
Port Scan:

Discovery scans the open ports on the device.
It finds:
Port 22 (SSH) is open.
Port 80 (HTTP) is open.
Classification Using Ports:

Port 22 indicates the device might be a Linux/Unix server.
Port 80 indicates it might be running a web application.
Based on this, Discovery applies a Linux Server Classification Pattern.
Deep Discovery:

Using SSH (enabled by Port 22), the MID Server logs in using credentials provided in Discovery settings.
It gathers:
OS type (e.g., Ubuntu 20.04).
RAM, CPU, and disk space details.
Installed applications and their versions.
Storing in CMDB:

The collected data is stored in the CMDB under the corresponding CI class (e.g., Linux Server).

#### Key Takeaway:
Port scanning is not a separate step after identifying the device type; it’s integral to the classification process.
Ports are scanned immediately after the device responds to the initial probe.
The information gathered from open ports helps determine the type of device and guides the subsequent probing steps.



### **Credentials

Credentials play and important role in discovery and its often the most challenging part.
Before we begin with discovery we must gather the credentials that must be used by the MID server to access and gather information about the devices we are expected to discover.

Credentials are stored in ServiceNow credentials table. Once we are able to connect to a particular device type with a credential, a record in credential affinity table gets created which will be tried first when trying to access the device next time.

### **MID Server Architecture
![[Pasted image 20250131164653.png]]


### **Discovery Ports and Cred required**
![[Screenshot (28).png]]
![[Screenshot (29).png]]

### **Discovery Life Cycle**
![[Pasted image 20250206164303.png]]![[Pasted image 20250210112937.png]]
### **Horizontal discovery Flow**
![[Pasted image 20250209003412.png]]

### **Phases of Discovery**
1. **Scan Phase**: when Discovery is initiated, a single **Shazzam** probe is launched (placed in the ECC Queue as an output probe), scanning for open TCP ports (_"Are you there?"_) on network-connectable nodes. An attempt is made to determine device type based on activity known to exist on these ports (_"how will I classify you?"_). For example, UNIX-based platforms usually use port 22 for SSH; Windows uses port 135 for WMI communication.
    
    Discovery makes certain assumptions about the devices, applications, and processes running on these ports and launches appropriate classify probes to find out more (e.g.: _"if you respond to WMI, I will classify you as a Windows device"_).
    
2. **Classification Phase**: classify sensors process data returned from classify probes (one per device), comparing against criteria for each class of device, attempting to classify the device specifically, e.g.: distinguishing if a Windows platform is Windows 2003, Windows 2008, Windows 2012 etc.
    
3. **Identification Phase**: Patterns are launched via the Horizontal Discovery Probe. Using CI identifiers, an attempt is made to match information against CMDB records (_"have I seen you before?"_). Depending upon if a matching CI is found (or not), a new record is created or an existing CI is updated.
4. **Exploration Phase**: Patterns are gathering more detailed information (_"what else can you tell me about yourself?"_) to populate CI attributes accordingly, both hardware and software characteristics.

So Discovery uses probes and patterns to explore any given computer or device, starting first with basic probes and then using more specific patterns as it learns more.

### **Additional notes about Modules in DIsco**
#### Behavior
A Discovery Behavior determines what probes Shazzam launches and from which MID Servers these probes are launched. As an alternative to specifying a single MID server, a Behavior can assign different tasks to multiple MID Servers on the same IP address segment or on different network segments. Behaviors allow an administrator to target specific types of devices within a discovery schedule such as Windows or Unix only type devices.
#### Process classifiers
A process classification allows Discovery to create a particular CI type such as an application from information gathered during the identification and exploration phases. Applications can be classified based on running processes and a relationship can be built between the application and the hardware which can be visualized on the dependency view map.
Discovery classifies processes during the exploration phase. Like device classification, process classification has its own criteria and the ability to launch additional probes. A pending process classification requires review to convert it to a standard process classification