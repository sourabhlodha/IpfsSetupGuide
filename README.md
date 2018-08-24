# IPFS SETUP GUIDE for Ubuntu

# IPFS Guide For Private Repository

## Create A folder 
###### mkdir ipfscluster

## Download IPFS for ubuntu
###### wget https://dist.ipfs.io/go-ipfs/v0.4.13/go-ipfs_v0.4.13_linux-amd64.tar.gz

## Uncompress the achieve File
###### tar xvf go-ipfs_v0.4.13_linux-amd64.tar.gz

## Switch Directories
###### cd go-ipfs

## Install to /usr/locl/bin
###### sudo ./install.sh

## Initialise the node configuration
###### ipfs init


Ensure IPFS starts when the machine boots, create a systemd service for it. 
As root, 
###### create the file /lib/systemd/system/ipfs.service with the following contents:
[Unit]
Description=IPFS daemon
After=network.target

[Service]
User=sourabh
Group=sourabh
ExecStart=/usr/local/bin/ipfs daemon
Restart=on-failure

[Install]
WantedBy=multi-user.target


# NOTE: Modify the User= and Group= clauses above with your particular user. 

## Start the IPFS service:
###### sudo systemctl start ipfs

## Enable the service at system startup:

###### sudo systemctl enable ipfs
## Optionally, check the IPFS service logs:

###### sudo journalctl -u ipfs

# Run ipfs init
###### folder created in /root/.ipfs
