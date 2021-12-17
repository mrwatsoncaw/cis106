## Final Project 
Step 1 - sudo apt install Samba

Step 2 - cd into samba directory

Step 3 - Look at the configuration to samba- type - nano smb.configuration

Step 4 - Move configuration file -- sudo mv smb.conf smb.conf.bak

Step 5 - Stop the service because samba no longer has a conf. file- type- sudo systemctl stop smbd

Step 6 - Check status to make sure it stop- sudo systemctl status smbd

Step 7 - Create conf. file-- sudo nano smb.conf to create a configuration. It will be empty to create a file
Create server Globally 

Step 8 - Create shares file - type -- sudo nano shares.conf. It will be empty. Create the second file that includes the shares to open the 
network for other users to share. Create 2 files one for public and one for private.

Step 9- Create directories that would be shared--type sudo mkdir -p /share/public_files and than sudo mkdir /share/private_files

Step 10- Create the group and the user- type - sudo groupadd --system smbgroup. 
Next create the user -- type sudo useradd --system --no-create-home --group smbgroup -s /bin/false smbuser It prevents anyone from logging in as the user.

Step 11 - Change the permissions of the shared directories-- type-- sudo chown -R smbuser:smbgroup /share

Step 12 -- To activate samba and see if its working --type-- sudo systemctl start smbd

