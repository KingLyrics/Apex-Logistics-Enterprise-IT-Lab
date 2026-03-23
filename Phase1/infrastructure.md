# Building the Infrastructure
- Below are the configurations and build for this project. 

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


## Accounts Creation
-  Accounts were created on setup.
- `apex-sysadmin` -> For the Linux Server
- `Adminstrator` -> For the Windows Server
- `ApexBox` -> For the Windows client temporary account until it is connected to the domain

# Network Configuration Setup
- Since this is running on my local virutal machine setup, I need to find a way for all three virutal machines to identify each other. 
- As a result I have decided to use the NAT Network adapter method.
- This allows me to create a private network of many virutal machines that can communicate with each other while stil having access to the internet using the host(my computer)


## Network Configuration
- Nat Network Name: `APEX-LINK`
- Ipv4 Prefix: `192.168.65.0/24`
- Default gateway: `192.168.65.1`
- Each machine will be connected to the Nat network.
- Static IP Addresses will be configured.


# Checks and Additional configuration
- Checking that the date and time are correct.
- On `Alama Linux`: I ran `timedatectl` to ensure date and time were accurate.
- Correcting date and time on the windows server.


# Assiging Static IP Addresses
## Alama Linux
- To assign a static IP address for the linux sever I used the GUI nmtui to do it.

- Static IP Address Assigned: `192.168.65.20/24`
- Default gateway: `192.168.65.1`

- After configuring and saving the IP address assigned, I had to restart the network manager using: `sudo systemctl restart NetworkManager`

- Once restarted, it showed that it was given another dynamic address from the NAT network. I forgot to turn off  DHCP server.

- So i deleted the ip address using:
`sudo ip addr del 192.168.65.5/24 enp0s3`
- This wasn't working as it said either local is duplicate.
- Error was due to me forgetting to add `dev` to the syntax.
- Correct syntax: `sudo ip addr del 192.168.65.5/24 dev enp0s3`

## Windows Server
- Static IP : `192.168.65.10`
- Preferred DNS Server: `192.168.65.10`
- Full Computer Name: `Apex-Win-Serv`
- We want the windows Server to be the DNS Server


## Windows Client
- Static IP : `192.168.65.30`
- Preferred DNS Server: `192.168.65.10`
- Turned on the same firewall inbound rule for the windows client as well.


## Testing computers can talk to each other
- Couldn't ping the windows server and linux server.
- Had to allow the firewall inbound rule for tcmp to be enabled. See screenshots for more.