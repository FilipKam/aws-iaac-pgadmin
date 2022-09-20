# About
This IaaC CFN stack creates new EC2 instance with Security Group allowing SSH access from specified public IP address. Egress traffic is allowed to specified security group ID.

# pgAdmin4 installation
## Add pgAdmin 4 repository - UserData
`sudo sh -c 'echo "deb https://ftp.postgresql.org/pub/pgadmin/pgadmin4/apt/$(lsb_release -cs) pgadmin4 main" > /etc/apt/sources.list.d/pgadmin4.list'`
## Add Public GPG Key - UserData
`sudo curl https://www.pgadmin.org/static/packages_pgadmin_org.pub | sudo apt-key add`
## Update Ubuntu - UserData
`sudo apt update && sudo apt upgrade`
## Install pgAdmin4 on Ubuntu - UserData
`sudo apt install pgadmin4-web`
## Configure the pgAdmin user account - MANUAL STEP
`sudo /usr/pgadmin4/bin/setup-web.sh --yes`
## Access pgAdmin Web Interface - MANUAL STEP
In the URL box type: `http://your-server-ip-address/pgadmin4`
## Connect PostgreSQL Database - MANUAL STEP
- On your pgAdmin Dashboard, click on the Add New Server.
- Enter the name of the server and click on the Connection tab.
- Enter the PostgreSQL server hostname or IP address and the port number.
- Enter the PostgreSQL username and password.
- Click on the Save button to save the server.