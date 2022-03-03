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

The next step is to remotely connect using the following commands
1. The first step was to install mysql-client on the client server and mysql-client.
2. After which I had to create a user on the mysql-server database using this code below.

`CREATE USER 'me'@'myIP' IDENTIFIED BY 'password'`.

3. The next step is to actually 

`mysql -h "IP-ADDRESS" -u "username" -p`