---
title: Choose Right EC2 Instance for Hosting a Database
date: 2020-07-10
math: false
diagram: false
tags: [aws, ec2, database]
markup: mmark
image:
  placement: 1
  #caption: 'Image credit: [**Unsplash**](https://unsplash.com/photos/CpkOjOcXdUY)'
  focal_point: ""
  preview_only: false
---

Choosing the right ec2 instance for your database is really important. The cloud services are selling like hot cakes and by far the AWS - Amazon Web Services has the biggest pie of the cake.  The public cloud provides you very high flexibility and ability to spin up the infrastructure within minutes rather than working through corporate procurement and spend weeks and months of time.  The three most used and basic infrastructure need why people move to cloud are

- Compute infrastructure
- Storage
- Databaases

This article helps you deal with the first and the third aspect of the AWS cloud.

## The need for databases:

The databases for years have been the backbone for any application.  With recent times the need for the data storage has increased many folds and so has the variety of databases.  In most part they can be categorized into 2 broad categories

- Relational Databases
- Non-Relational Databases ( Call it No-SQL) databases.

Most of the cloud providers like AWS provides a plethora of database options where you do not have to manage the infrastructure for your database.  A few of the database options offered by AWS

| DB Type | AWS Offering | Purpose |
| --- | --- | --- |
| Relational | Amazon Aurora, Amazon RDS, Amazon Redshift | Traditional OLTP and data warehouse system |
| Key Value | Dynamodb | High Traffic apps like webapps, gaming etc |
| Document | Amazon DocumentDB | To store content of blog etc |
| Time Series | Amazon Timestream | Telemetry , Logs or IOT Data |
| Ledger | Amazon QLDB | Blockchain needs like banking, cryptocurrency etc |
| Graph | Amazon Neptune | Social Networking , Fraud detection etc |

If you see the list above it should be able to cover most of your needs for the database that are provided as managed service.  So why do you need to host a database server on a self managed virtual machine (EC2)

## Why to use EC2 to host your database

Though AWS provides you with a variety of managed databases, there may be some need when you want to host your own database.

### Applications that do not support RDS or other databases:  
If you want to run an application that does not support RDS you have no choice but to use the database hosted on an EC2 machine.  For eg. To run a PowerBI Report Server you have to host the SQL Server on the EC2.

### When RDS does not support a DB feature:  
Though the RDS offers you the basic database services, it may not offer the auxiliary services.  For eg. if you want to use the Database Scheduler  or SSIS or SSAS for SQL server, you cannot use RDS

### When you need fine grained control:  
The managed databases do not offer you flexibility in terms of type of storage, CPU, LDAP authentication, parameter setting etc.  When you want to be in full control for your database, RDS or other managed databases may not be the best choice

### Specialized Databases : 
When you need to host other databases not provided as managed DB.  For eg. Cassandra, HBase, Exasol, Neo4J, SAP Hana etc.


## Factors to keep in mind :

Before we jump into exact type of instances, there are a few factors we need to consider :

- Always start with small footprint and increase resources as you need.  There is a cost to everything in the cloud and scaling up is easier than data center
- Never underestimate the IO :  The disk IO is an important factor and the storage attached depends on the instance type.  _For detailed comparison of EC2 IO visit :_ [_https://www.aws-cost.com_](https://www.aws-cost.com)
- Network bandwidth:  This is often ignored factor in the on-prem databases, as the network speed remains same irrespective of the machine size.  However in cloud it&#39;s a different story altogether.  The network speed is also determined by instance type/size.  _For detailed comparison of IO network speeds visit :_ [_https://www.aws-cost.com_](https://www.aws-cost.com)
- CPU v/s Memory intensive workloads:  The EC2 instances are tied to a specific ratio of CPU to memory unlike a server in the data-center, where you have flexibility to choose your own level of CPU and network. _For detailed comparison of CPU &amp; RAM for EC2 visit :_ [_https://www.aws-cost.com_](https://www.aws-cost.com)

## Choosing the right EC2 for your database :

While selecting the right EC2 instance there are a multitude of factors that affect your decision

- **Type of Database :** This is the most important factor that determines your choice of database.  A RDBMS may have different resource needs v/s in-memory database v/s no-sql database
- **Type of workload :** IO vs CPU vs Memory intensive workload.  This is related to the type of database as well.

The following summarizes the best instance type to use for your Database.  Refer to [_https://www.aws-cost.com_](https://www.aws-cost.com)

### Memory Intensive Workloads :
Most RDBMS are memory intensive.  For moderate to large size use the **r-family** instances.  The latest subfamily(r4 vs r5) the better it is in terms of cost and resources.

### IO Intensive Workloads :
For a database that has need for higher io use the **i-family** instance. For eg. a cassandra database or an HBase database

### In-Memory databases :
For in-memory databases like SAP Hana or Apache Ignite or Redis Cache use the **r-family** or **x-family** instance.  An x1e.32xlarge has 3,904 GiB        RAM.

### Nimble Size Database :
For small sized database use the m-family or c-family instance.

A> No matter what instance fits your needs make sure to control your costs using Reserved instances and plan for disaster recovery.
