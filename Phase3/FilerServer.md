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


# Joining domain
- Packages to install
 `dnf install realmd sssd oddjob oddjob-mkhomedir adcli samba-common-tools -y`
 - Most packages were already installed except `oddjob` and `oddjob-mkhomedir`.

- used realm to discover the domain
`realm discover apexlogistics.local`
- join AD
` realm join  apexlogistics.local -U Administrator`

- Check for user id
` id ekom.admin@apexlogistics.local`
- I prefer to leave the domain inclusive when checking instead of `id ekom.admin`



# Creating folders
- folders will be stored under /srv/companyshares/{OU}
```
mkdir -p /srv/companyshares/Finance
mkdir -p /srv/companyshares/HR
mkdir -p  /srv/companyshares/Operations
```

# setting permissions
- Permissions were set according to the groups created earlier
` chown -R root:"{Group-Name}@apex.logistics.local" /srv/companyshares/{OU} `


# Configure Samba
- To ensure that it works on the windows the `/etc/samba/smb.conf` need to be configured
- Enbaling smb
`systemctl enable smb --now`

- Allow through firewall 
`firewall-cmd --permanent --add-service=samba`
`firewall-cmd --reload`

# Install Winbind
`sudo yum install -y samba-winbind samba-winbind-clients krb5-workstation`

# Modifications
- Edited smb.conf and /etc/nsswitch.conf accordingly. 
- Screenshots for both are supplied.
