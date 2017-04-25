===================
Prerequisite
===================
Please make sure that your Vagrant version is at least 1.8 
and VirtualBox is at least 4.26 
We’ll use it to bring up a virtual machine with CentOs 7

Creating a Vagrant virtual machine is easy.
1 vagrant plugin install vagrant-cachier


The first command is not mandatory, but it will help speeding up the creation of new VMs. It caches
all packages that are being used so that the next time we need them, they are obtained from the
local HD instead being downloaded. The second command does the “real” work. It brings up the
VM called dev. The first attempt might take some time since everything, starting with the base box,
needs to be downloaded. Bringing up this VM will be much faster each consecutive time. Bringing
up any other Vagrant VM based on the same box (in this case bento/centos-7.2) will be fast.
 

===================
Descrpition
===================
1.oracledb（200.200.200.200） 

Connect database with following setting:
  hostname: localhost
  port: 49161
  sid: xe
  username: system
  password: oracle
  Password for SYS & SYSTEM

oracle
  Login by SSH
  
  ssh vagrant@200.200.200.200
  ssh root@localhost -p 49160
  password: admin
  Support custom DB Initialization

# Reference
https://hub.docker.com/r/wnameless/oracle-xe-11g/

2.mysqldb（200.200.200.201）
https://hub.docker.com/r/mysql/mysql-server/

  hostname: 200.200.200.201
  port: 49162
  sid: ude
  username: ude
  password: ude
  Password for SYS & SYSTEM
  
Login by SSH<br>
ssh root@localhost -p 49160
password: ude

# Reference
https://hub.docker.com/r/wnameless/mysql-phpmyadmin/

3.postgresql（200.200.200.202）

Open http://200.200.0.202:49161/phppgadmin  in your browser with following credential:<br>
username: ude
password: ude

Login by SSH 
ssh root@localhost -p 49160 
password: admin

# Reference
https://hub.docker.com/r/wnameless/postgresql-phppgadmin/

4.MSSQL（200.200.200.203）
     port: 1433
     username: sa
     password: Ude123@iisi

5.MongoDB（200.200.200.204）
    port: 49161
     
