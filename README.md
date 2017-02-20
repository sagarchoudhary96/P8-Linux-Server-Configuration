# Linux Server Configuration

### Project Overview
> A baseline installation of a Linux server and preparing it to host our web applications, 
securing it from a number of attack vectors, installing and configuring a database server, and deploying 
our one of your existing web applications onto it.

### Why this Project?
> This Project provides deep understanding of exactly what our web applications are doing, 
how they are hosted, and interats with multiple systems. In this Project, we will  turn a brand-new, 
bare bones, Linux server into the secure and efficient web application host needed by Our Applications.

#### Link to Project: [ItemCatalog](http://ec2-52-33-104-60.us-west-2.compute.amazonaws.com)

* **Public IP Address:** 52.33.104.60
* **Accessible SSH port:** 2200

## Steps to Configure Linux server
#### 1. Create Development Environment Instance
  * [Create new development environment here.](https://www.udacity.com/account#!/development_environment)
  * Download private key provided and note down your public IP address.
  
#### 2. Launch VM and access SSH to the instance
  * Move the private key file into the folder ~/.ssh (where ~ is your environment's home directory).
  
  ```
    $ mv /(current_private_key_address)/udacity_key.rsa ~/.ssh/
  ```
  * Change the key permission so that only owner can read and write
  
  ```
    $ chmod 600 ~/.ssh/udacity_key.rsa
  ```
  * SSH into the instance
  
  ```
    $ ssh -i ~/.ssh/udacity_key.rsa root@public_IP_address
   ```
   
#### 3. Create New User
  
  * Add User grader
  
  ```
   $ sudo adduser grader
  ```
  * Give Sudo Access to grader
  
  ```
   $ sudo nano /etc/sudoers.d/grader
  ```
  * Add following line to this file
  
  ```
   grader ALL=(ALL:ALL) ALL
  ```
  * To prevent the "sudo: unable to resolve host" error
  
   i. Edit the hosts file:
   
   ```
    $ sudo nano /etc/hosts
   ```
   ii. Add the host:
   
   ```
    $ 127.0.1.1 ip-XX-XX-XX-XX
   ```
