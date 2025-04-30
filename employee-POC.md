
# POC of Employee-API

![image](https://github.com/user-attachments/assets/75de11da-e895-4a24-a312-ad9824da4d59)


### Author
| Created     | Version | Author        | Modifed | Comment           | Reviewer         |
|-------------|---------|---------------|-------|------------|------------------|
| 25-04-2025  | V1      | Yuvraj Singh |  | Internal Review   | Siddharth Pawar  |

## Table of Contents

<details>
<summary>1. Introduction</summary>

- [Introduction](#introduction)  
- [Supported Features of the Employee API](#supported-features-of-the-employee-api)

</details>

<details>
<summary>2. Environment Setup</summary>

- [Pre-requisites](#pre-requisites)  
- [System Requirements](#system-requirements)  
- [Important Ports](#important-ports) 

<details>
<summary>➤ Dependencies</summary>

- [Dependencies](#dependencies)  
  - [Buildtime Dependency](#buildtime-dependency)  
  - [Runtime Dependency](#runtime-dependency)

</details>
</details>

<details>
<summary>3. Installation Guide</summary>

- [Step-by-step Installation](#step-by-step-installation)  
  - [Access employee-api Server](#access-employee-api-server)  
  - [Installing Dependencies for employee-api](#installing-dependencies-for-employee-api)  
    - [Go-lang](#go-lang)  
    - [ScyllaDB](#scylladb)  
    - [Redis](#redis)  
    - [Jq](#jq)  
    - [Make](#make)  
    - [Golang-migrate](#golang-migrate)

</details>

<details>
<summary>4. Configuration</summary>

- [Runtime Configuration](#runtime-configuration)  
  - [ScyllaDB Configuration](#scylladb)  
  - [Redis Configuration](#redis)  
- [Create KEYSPACE in Scylla](#create-keyspace-in-scylla)  
- [Redis CLI Permissions](#redis-cli-permissions)

</details>

<details>
<summary>5. Code Setup</summary>

- [Working with employee-api Git Repository](#working-with-employee-api-git-repository)  
  - [Migration Configuration](#migration-configuration)  
  - [Config File Setting](#config-file-setting)  
  - [Configure main.go](#configure-maingo)

</details>

<details>
<summary>6. Testing & Execution</summary>

- [Testing Go Modules](#testing-go-modules)  
- [Run the API](#run-the-api)  
- [Check Working](#check-working)

</details>

<details>
<summary>7. Wrap-up</summary>

- [Conclusion](#conclusion)  
- [Contact](#contact)  
- [References](#references)

</details>


## Introduction

Welcome to the Employee-API POC. Employee REST API is a golang based microservice which is responsible for all the employee related transactions in the OT-Microservices. This application is completely platform independent and can be run on any kind of platform. [For Employee API detailed document refer this document](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-79-Adil/ot-ms-understanding/employee/documentation/README.md).

## Supported Features of the Employee API:

| Component              | Description                                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------------------|
| **Go**                 | A fast, lightweight web framework providing routing, middleware handling, and API request management.       |
| **ScyllaDB**           | Primary database for storing all employee data; a high-performance NoSQL solution compatible with Cassandra, ensuring scalability and fast data access. |
| **Redis (Optional)**   | Cache layer for storing frequently accessed employee data, reducing database load and improving response times. |
| **Swagger/OpenAPI**    | Integrated API documentation, allowing for easier interaction with and understanding of endpoints, data structures, and testing. |
| **Database Migrations**| Managed with the Migrate, enabling database schema changes and maintaining consistency across environments. |

## Pre-requisites 
The application doesn't have any specific pre-requisites except the database connectivity. Additionally, we can add Redis as cache system but it's not part of the mandatory setup and Migrate to setup table in ScyllaDB.

- ScyllaDB
- Migrate
- Redis
- Go 
- Make

## System Requirements
| **Requirements** | **Details** |
|---------|---------|
| OS |  Ubuntu 22.4 |
| Vm type | t2 medium |
| Disk space | 15 GB |

## Important Ports
| Port No | Description | Traffic | 
|:----:|:----:| :----: |
|8080 | Employee API port | Inbound |
|22   | SSH | Inbound | 
|9042 | ScyllaDB | Inbound  |
|6379 | Redis | Inbound |

## Dependencies
### Buildtime Dependency
| Buildtime  Dependency  | version |
|:-----------------------:|:--------------------:|
| Golang | 1.18 |
| Migrate | 4.15.2 |

### Runtime Dependency
| Runtime Dependency | version |
|:-----------------------:|:--------------------:|
| ScyllaDB | 6.2 |
| Redis | 6.0.16 |


## Step-by-step installation
This guide explains how to set up a virtual machine (VM), install dependencies, configure the database and caching services, and run the `employee-api` application. Follow each step carefully to ensure the application is correctly installed and functioning.

![image](https://github.com/user-attachments/assets/4edb0197-26d2-4239-a077-e5b215728f1a)


### Access employee-api server

- *Connect to your employee-api server*

```
ssh -i path-to-your .pem key ubuntu@employee-api-public-ip
```
![image](https://github.com/user-attachments/assets/5e8f3e15-d7c9-4644-8926-e8f6761c5e45)

---

## Installing dependencies for employee-api

- *Update your server* [Go to this link for ubuntu basic commands.](https://github.com/snaatak-Downtime-Crew/Documentation/blob/main/common_stack/operating_system/ubuntu/sop/commoncommands/README.md#1-basic-system-commands)

---

### Go-lang

- *Install the go-lang package.* [Go to this link for Go-lang installation guide](https://github.com/snaatak-Downtime-Crew/Documentation/blob/main/common_stack/application/golang/installation/guide/README.md#2-golang-installation-guide-step-by-step-in-ubuntu)

---

### ScyllaDB

---

- *Install ScyllaDB* [Go to this link for ScyllaDB installation guide](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-88-Adil/ot-ms-understanding/scylladb/poc/README.md#step-by-step-installation-of-scylladb)

---

### Redis

---

- *Install redis-server* [Go to this link for Redis-server installation guide](https://github.com/snaatak-Downtime-Crew/Documentation/blob/SCRUMS-84-PRINCE/ot-ms-understanding/redis/poc/README.md#1-install-redis-server)

---

### Jq
---

- *Install jq* [Go to this link for jq installation guide](https://github.com/snaatak-Downtime-Crew/Documentation/blob/yuvraj_scrums_38/common_stack/others/jq/sop/README.md#installation-guide)

---

### Make

---

- *Install make* [Go to this link for make installation guide](https://github.com/snaatak-Downtime-Crew/Documentation/blob/main/common_stack/others/make/sop/README.md#installation-on-linux)

---

### Golang-migrate

---

- *Install Golang-migrate* [Go to this link for golang-migrate installation guide](https://github.com/snaatak-Downtime-Crew/Documentation/blob/main/common_stack/others/migrate/sop/README.md#step-by-step-installation-guide)

---

## Runtime Configuration

---

### Scylla DB
---

1. *Open scylla configuration file*

```
sudo vi /etc/scylla/scylla.yaml  
```
![image](https://github.com/user-attachments/assets/fc34f7d1-4755-4991-9a19-adc841949741)

- *Changes to make:*  

```
rpc_address: localhost > rpc_address: instance_private_ip
```
![image](https://github.com/user-attachments/assets/08149281-4a55-4e7a-99ea-0523d1ae348d)

- *Also add the following at the bottom of the file to allow scylla db to be accessable with cassandra credentials.* 

```
authenticator: PasswordAuthenticator  
authorizer: CassandraAuthorizer
```
![image](https://github.com/user-attachments/assets/6ae7eec4-3f85-4da6-9576-2f472b8ed7b4)


- *Write and quit the file*

---

2. *Scylla dependencies installation and service file creation*

```
sudo /opt/scylladb/scripts/scylla_io_setup
```
![image](https://github.com/user-attachments/assets/6e182ee7-22d1-4b95-956b-684b2794d4c7)

---

3. *Enable scylla service file to be started after system reboot*

```
sudo systemctl enable scylla-server  
```
![image](https://github.com/user-attachments/assets/c8e6c338-4b70-45fa-aec7-7fe91809a4cc)

---

4. *Start the scylla server*

```
sudo systemctl start scylla-server
```
![image](https://github.com/user-attachments/assets/abcb98e4-8d75-43d7-9733-29069b1ee5c5)

---

5. *Confirm if the scylla-server is running or not*

```
sudo systemctl status scylla-server
```
![image](https://github.com/user-attachments/assets/44f43e70-5061-4638-89f9-11ed3d918b98)

---

### Redis

---

1. *Open redis configuration file*

```
sudo vi /etc/redis/redis.conf
```
![image](https://github.com/user-attachments/assets/b3ef38b1-7959-4ab9-a19e-f9e7280de3fc)


- *Changes to make:* 

```
# bind 127.0.0.1 ::1 > bind 127.0.0.1 instance_private_ip
```

![image](https://github.com/user-attachments/assets/f3466d4a-f135-42f4-b343-36bb298a08da)

> *Write and quit the file*

---

2. *Enable redis service file to be started after system reboot*

```
sudo systemctl enable redis-server  
```

![image](https://github.com/user-attachments/assets/ea4ad2a5-0f48-4123-847d-94f7a38377f1)

---

3. *Start the redis server*

```
sudo systemctl start redis-server
```

![image](https://github.com/user-attachments/assets/5de31e57-645e-4879-8f4f-d28fae911798)

---

4. *Confirm if the redis-server is running or not*

```
sudo systemctl status redis-server
```

![image](https://github.com/user-attachments/assets/8b56b15a-ef20-4e3e-856e-9140ca42448f)

---

## Create KEYSPACE in Scylla
---

- *Connect to ScyllaDB with username cassandra and password cassandra*

```
cqlsh <instance-private-IP> 9042 -u cassandra -p cassandra
```
![image](https://github.com/user-attachments/assets/f6617cf2-c18d-4587-af90-31869f3d8114)

---

### Inside cqlsh

---

1. *Create a scylla db user with superuser permissions and password 'password'*

```
CREATE USER scylladb WITH PASSWORD 'password' SUPERUSER;
```
![image](https://github.com/user-attachments/assets/a3069715-2b86-45ac-802d-a0feee02c8e8)

---

2. *Create a keyspace employee_db with one replication.*

```
CREATE KEYSPACE employee_db WITH REPLICATION = { 'class': 'SimpleStrategy', 'replication_factor': 1 };  
```
![image](https://github.com/user-attachments/assets/0234c538-69e4-49ab-be26-ae82498d4ac6)

---

3. *View all available keyspaces.*

```
DESCRIBE KEYSPACES;
```
![image](https://github.com/user-attachments/assets/0242807f-65d7-48c7-8cea-999445ee08ca)

---

4. *Quit cqlsh*
   
```
exit
```
![image](https://github.com/user-attachments/assets/04924ac8-3432-4310-a521-637ef4b510d2)

---

## Redis CLI permissions

---
1. *Access redis command line interface*

```
redis-cli
```

![image](https://github.com/user-attachments/assets/c5580187-e179-4b08-8ae9-4a372aafc977)

---

2. *Configure User Permissions and Authentication*

```
ACL SETUSER scylla on >password ~* +@all
```

![image](https://github.com/user-attachments/assets/c3885161-3206-4ed1-a768-97006f117b5e)

---
3. *List updated ACL rules*

```
ACL LIST
```

![image](https://github.com/user-attachments/assets/30724b10-e091-4bc9-a94e-0b19432d2930)

---

4. *Quit redis cli*
   
```
exit
```

![image](https://github.com/user-attachments/assets/6812490a-4dc1-4cfe-b15a-d74cccdf5566)

---

## Working with employee-api Git repository

---

1. *Clone the employee-api repository into our local system*

```
git clone https://github.com/OT-MICROSERVICES/employee-api.git  
```
![image](https://github.com/user-attachments/assets/e25dbc1c-32ff-4317-b26d-a788ab8b84eb)

---

2. *Move to employee api directory and lists the contents*

```
cd employee-api && ls
```
![image](https://github.com/user-attachments/assets/5b527dae-b813-480d-81af-2fe7ca872efb)

---

### Migration configuration

---

1. *Open the migrations file*

```
vi migration.json
```

![image](https://github.com/user-attachments/assets/e5b70030-4f55-4790-9de8-4f5e61514321)

---

2. *Replace the IP address with your actual private IP*

![image](https://github.com/user-attachments/assets/5ce9b348-3d77-4df6-8341-ab3ecc7fd115)

---

3. *Execute the migration.json file to configure database connection.*

```
make run-migrations
```

![image](https://github.com/user-attachments/assets/6210624d-23ce-45c0-ab72-5d6b8c259f2d)

---

### Config file setting

---

1. *Open config.yaml file* 

```
vi config.yaml
```

![image](https://github.com/user-attachments/assets/f39a4329-046e-4e39-8ec7-9018049b12dd)

---

2. *Replace the IP address with your actual private IP for both scylladb and redis*

![image](https://github.com/user-attachments/assets/97809e66-94cf-4369-a157-f6f02883e2cc)

---


### Configure main.go

---

1. *Open main.go*

```
vi main.go
```

![image](https://github.com/user-attachments/assets/29c77b81-c5a7-4f61-980b-0ef31d125723)

---

2. *Replace `localhost` with `<public-ip:8080>`*

![image](https://github.com/user-attachments/assets/1ed2b161-7e20-4fbd-88c4-9e6f62b383f8)

---

## Testing Go modules

---

1. *Perform coverage tests*

```
go test $(go list ./... | grep -v docs | grep -v model | grep -v main.go) -coverprofile cover.out  
```

![image](https://github.com/user-attachments/assets/6dbb8020-5fd7-4e69-9941-2b3e021e0791)
![image](https://github.com/user-attachments/assets/be135a84-f681-4a9f-8e36-916de6251e3a)

---

2. *Generate code coverage report in HTMLformat.*
   
```
go tool cover -html=cover.out
```

![image](https://github.com/user-attachments/assets/200ff568-b2d9-4494-825d-f602a0f4dd65)

---

## Run the API

- *Run the api*

```
go run main.go
```

![image](https://github.com/user-attachments/assets/dbc938af-c9c8-468e-9f4b-576cd953abe3)

---

## Check working

1. *Open a web browse and access this link.*

```
http://public-ip:8080/swagger/index.html
```

![image](https://github.com/user-attachments/assets/17307432-fd97-4b6e-8ad8-129a40ab7b1a)

2. *Click on post option and then 'try it out'*

![image](https://github.com/user-attachments/assets/aeda53ab-3115-42f2-9136-426017c46c32)

3. *Enter sample data and click on execute*

![image](https://github.com/user-attachments/assets/96081d28-3760-4d72-8c13-e0e276342829)

4. *If the response code is 200 then your data is successfully entered in the database and your setup is running well*

![image](https://github.com/user-attachments/assets/2174fde3-dfc3-4302-9ba5-06a802f30079)


## Conclusion

This Proof of Concept (POC) for the Employee API provides a detailed and structured approach to deploying a scalable and high-performing microservice. The document offers clear guidelines on system requirements, dependencies, and installation steps to ensure a seamless setup process. By leveraging modern technologies like Golang, ScyllaDB, and Redis, the API achieves optimal performance, scalability, and reliability.

## Contact

| Name| Email Address      |
|-----|--------------------------|
| Yuvraj Singh | yuvraj.singh.snaatak@mygurukulam.co |


## References

| Source                                                                                     | Description                                |
| ------------------------------------------------------------------------------------------ | ------------------------------------------ |
| [ScyllaDB Installation Guide](https://opensource.docs.scylladb.com/stable/getting-started/install-scylla/install-on-linux.html) | Comprehensive guide for installing ScyllaDB on Linux. |
| [Redis Installation Guide](https://redis.io/docs/latest/operate/oss_and_stack/install/install-redis/) | Step-by-step instructions for installationing Redis. |
| [Application Template ](https://github.com/OT-MICROSERVICES/documentation-template/wiki/Application-Template) | Document format followed from this link   | 
