---
title: Why Traditional ETL Tools Are Less Relevant Today
date: 2020-07-30
math: false
diagram: false
tags: [data engineering, ETL]
markup: mmark
image:
  placement: 1
  focal_point: ""
  preview_only: false
---

Data has been the primary reason why computers & Information Technology evolved. In the modern age Data is the key ingredient that is driving most businesses. The data storage & processing has come of an age. The things are changing rapidly at a very fast pace
I started my data journey almost two decades ago working on the traditional BI and ETL tools. However over the last few years there has been a major shift from these concepts & technologies.

### The Data Warehouse Age :

The data warehouse concept has existed for the last few decades. They were the really important way to organize your data to meet the BI and reporting needs. A few terms like Dimensional Modeling, Star Schema, SnowFlake Schema, ETL were coined and became popular in the community.
There were a plethora of tools that helped to transform and load the data in the data warehouses. Most of the tools offered Graphical User Interface (GUI) for how you model your ETL. A few players like Informatica, DataStage, SSIS etc were really important

### The Data Lake Age : 

With the ever increasing 3 Vs of data (Velocity, Variety, Volume), it started difficult to fulfill business needs with traditional data warehouses. Some argue Data Lakes would replace traditional Data Warehouse others argue they complement them. However one thing is unanimous that Data Lakes have become an important part of data transformation.

## Why traditional ETL Tools are becoming less relevant

### Variety of Data :  
Traditionally the data was mostly structured and ETL tools excelled at processing the data. These tools are not good at handling semi-structure & unstructured data.

### Volume of Data :  
Data volume is increasing exponentially. The traditional ETL tools cannot handle this with the scale up architecture.

### Velocity of Data : 
The Streaming data coming from the sources like IOT, Telemetry, ClickStream is more real time. It is difficult to process it using traditional ETL tools designed for Batch processing.

### Distributed Computing : 
Hadoop floated the idea of taking the compute(program) to data instead of bringing data to the compute. The traditional ETL tools used the same concept of moving data to compute on scale-up architecture. This made it difficult to use the modern distributed scale out architecture

### Relational to NoSQL Shift : 
The Sources and Destinations have become much more varied. This does suite the Traditional ETL Tools.

### Emergence of Cloud & ServerLess : 
Cloud has been a game changer. The early ETL tools were designed for persistent infrastructure. They are not best suited for the cloud ecosystem.

The traditional ETL players are trying to adopt to newer ecosystem. How much they succeed only time will tell

A> Nevertheless, in my opinion the structured databases & processing needs are here to stay for the foreseeable future. So it would be an exaggeration to say these tools are dead, but for sure they are becoming less & less relevant everyday.
