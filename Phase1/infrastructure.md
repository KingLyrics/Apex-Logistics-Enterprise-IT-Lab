# Building the Infrastructure
- Below are the configuration and build for this project. 

## OS Installation
- Installed Windows Server 2025, AlamaLinux and Windows 11 Pro edition.
- Screenshots of installation are located in the `screenshots/phase1`
- Snapshots were also taken of the fresh install. For disaster recovery purposes.

### Windows Server OS Configuration
- `Base Memory: 2048 MB`
- `Processors: 10`
- `Display: 256MB`

### Alama Liniux OS Configuration
- `Base Memory: 2048`
- `Processors: 6`
- `Display:256MB`

### Windows Client OS Configuration   
- `Base Memory: 4096`
- `Processors: 9`
- `Display: 256MB`

# Network Configuration Setup
- Since this is running on my local virutal machine setup, I need to find a way for all three virutal machines to identify each other. 
- As a result I have decided to use the NAT only adapter method.
- This allows me to create a private network of many virutal machines that can communicate with each other while stil having access to the internet using the host(my computer)


## Network Configuration
- Nat Network Name: `APEX-LINK`
- Ipv4 Prefix: `192.168.65.0/24`
- Default gateway: `192.168.65.1`
- Each machine will be connected to the Nat network.
- Static IP Addresses will be configured.