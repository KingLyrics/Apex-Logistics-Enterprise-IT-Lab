# Troubleshooting

- Failed to access the file server from the windows client. 
- The login page comes up but it doesn't allow for access regardless of who's username is there. 
- I left domain and will try again. Doing some research i found out that winbind is helpful. I'll try and see. 
-  I installed the recommended packages but faced more challenges

- I needed to configure the /etc/samba/resolv.conf file better
updating the:
realm
idmap
workgroup
 
- net ads join -U Administrator was not working because i had not configured the file accordingly. 
- Was able to fix it but now a new error showed showing NT_STATUS_uncessful
- resolved by rejoining the network.

# Ticket
- New ticket raised, maria from accounting  has logged in and accessed the file server now she cant write in the accounting folder. 
- She doesn't have acccess to the other folders which is good.
- turns out that SELinux is blocking writes  so i had to run the command
- ran chmod -R 2770 
- resolved


- All users can access their respective files.