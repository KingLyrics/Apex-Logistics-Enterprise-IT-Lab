# Internal Web Server
- This section will talk about the installation and creation of the apexlogistics web server

# Install httpd
 `dnf install httpd -y`


# start the service 
`systemctl enable httpd --now`


# Firewall settings 
`firewall-cmd --permanent --add-service=http`
`firewall-cmd --reload`

# edit the default website

- cd to `/var/www/html`
- nano `index.html`
- Asked AI to create a static webpage to speedup development for this project.
- I could create the webpage but that would take too much of my time as my focus is on system administration.


# edited nameserver
- Edited `system32/drivers/etc/hosts`
- can now be accessed using `apexlogistics.internal`

 *** side note: configured the profile i created called "ekom.admin" to have admin priveleges so i don't have to keep using my administrator account to handle admin tasks.  
