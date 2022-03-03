# CLIENT-SERVER ARCHITECTURE WITH MYSQL
---
In this task, I will demonstrate a basic Client-Server Relationship using mySQL Relational Database Management System.

1. The First step is to configure two Linux-based virtual servers(E2 instances in AWS).

2. On both servers, I installed mySQL and named them mysql-Client and mysql-Server.

3. The next step is to rename the two instances on the AWS instances here is the instances below.
![name](./images/name.png)

4. The two AWS instances were configured so that the hostname is configured using this code.

`hostnamectl sethostname mysql-Client`

![name](./images/comb-server.png)

These are the steps necessary to demonstrate a basic Client-server architecture using MYSQL. 
1. The first step was to install mysql-client on the client server and mysql-client.

2. After which I had to create a user on the mysql-server database using this code below.

`CREATE USER 'me'@'mysql-client-IP' IDENTIFIED BY 'password'`.


3. I used the local IP address of the mysql-server to allow communication between the two EC2 instances. using this code but first step 4 had to be done.

`mysql -h "IP-ADDRESS" -u "username" -p`

4. The next step is to actually configure the inbound rules to communicate since both EC2 virtual servers are located in the same local virtual network, so they can communicate with each other using the same IP address. 

5. The next step is to configure the mySQL server to allow connection from hosts, using this code.

`sudo vi /etc/mysql/mysql.conf.d/mysqld.cnf`

In this file, the bind address had to be changed to "0.0.0.0"

6. After which the mysql service was restarted, using this code.

    `sudo systemctl restart mysql`

7. The final step is to enter the mysql interactive terminal and grant access to the user added "me"
the IP-address of each EC2 was gotten after installing net-tools and typing ifconfig
    `GRANT ALL PRIVILEGES ON *.* TO 'username'@'IP-address';`

    `FLUSH PRIVILEGES;`


