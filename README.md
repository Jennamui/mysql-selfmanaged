# mysql-selfmanaged

Cloud Environment: GCP

How to setup a new VM with mysql:

1. Create new VM instance in GCP or Azure

-machine type: e2-micro

-Architecture: x86/64

-Firewalls: HTTP and HTTPS traffic On

-Boot disk image: ubuntu 

-All else is default settings

2. Add port 3306 by creating a new firewall rule

-Ingress

-Target: apply to all

-IP Ranges: 0.0.0.0

-Ports: tcp:3306

-Priority: 1000

3. Connect to VM

4. sudo apt-get update

5. sudo apt install mysql-server mysql-client

6. Log in: sudo mysql

7. Create user 'name'@'%' identified by name123

8. Confirm: select user from mysql.user;

9. Grant privileges: grant all privileges on *.* to 'name'@'%' with grant option

10. Test local user connection: mysql -u name -p

11. Create database tempdata;

12. show databases;

13. creating tables: 
use {database name}c
reate table table_name(var1 varchar(255), var2 varchar(255));

14. Updating mysql configuration to enable connections: sudo nano /etc/mysql/mysql.conf.d/mysqld.cnf

change bind address: 0.0.0.0

15. Restart mysql: /etc/init.d/mysql restart
