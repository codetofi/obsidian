![[Pasted image 20250210111447.png]]



1. **Scan Phase: when Discovery is initiated, a single Shazzam probe is launched (placed in the ECC Queue as an output probe), scanning for open TCP ports (_"Are you there?"_) on network-connectable nodes. An attempt is made to determine device type based on activity known to exist on these ports (_"how will I classify you?"_). For example, UNIX-based platforms usually use port 22 for SSH; Windows uses port 135 for WMI communication.**
    
    **Discovery makes certain assumptions about the devices, applications, and processes running on these ports and launches appropriate classify probes to find out more (e.g.: _"if you respond to WMI, I will classify you as a Windows device"_).**
    
2. **Classification Phase: classify sensors process data returned from classify probes (one per device), comparing against criteria for each class of device, attempting to classify the device specifically, e.g.: distinguishing if a Windows platform is Windows 2003, Windows 2008, Windows 2012 etc.**
    
3. **Identification Phase: Patterns are launched via the Horizontal Discovery Probe. Using CI identifiers, an attempt is made to match information against CMDB records (_"have I seen you before?"_). Depending upon if a matching CI is found (or not), a new record is created or an existing CI is updated.**

4. **Exploration Phase: Patterns are gathering more detailed information (_"what else can you tell me about yourself?"_) to populate CI attributes accordingly, both hardware and software characteristics.**



![[Pasted image 20250210171358.png]]