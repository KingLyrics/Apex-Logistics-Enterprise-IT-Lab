# File server creation

- This page will talk about installing samba and the configuration of the Linux server.

- Sudoed into root to stop retyping sudo.
- Installed samba using: `dnf install samba`
- Typed in `hostnamectl` to check if the host name has been assigned. If unset then i need to set it before joining the active directory.


# Set hostname
- Set the host name using: `hostnamectl set-hostname lnx-fileserver`

# Set DNS 
- There are two ways to do this. Using the nmtui interface and changing the /etc/resolv.conf
- I chose the latter way for this.
- The file now looks like 
```     
  search apexlogistics.local
  namserver 192.168.65.10 
```
- Then restart the network manager using: `systemctl restart NetworkManager` to validate changes
- pinged to test: `ping apexlogistics.local` -> Was successful.