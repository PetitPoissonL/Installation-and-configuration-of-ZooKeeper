# Installation and configuration of ZooKeeper for the project [Spark real-time project](https://github.com/PetitPoissonL/Spark_Streaming_Real_Time)
This guide provides detailed steps to install and configure Apache ZooKeeper on a cluster of three servers: `hadoop102`, `hadoop103`, and `hadoop104`. ZooKeeper is a high-performance coordination service for distributed applications.

## Prerequisites

Ensure the following prerequisites are met on all three servers:

- Linux-based environment (CentOS 7.5)
- Java JDK installed (version 1.8.0_212)
- Network connectivity between all three servers
- Sufficient permissions to install and configure software

## Step 1: Download ZooKeeper

Perform the following steps on each server (`hadoop102`, `hadoop103`, `hadoop104`):

1. Create 'module' and 'software' folders under the '/opt' directory

```
mkdir /opt/module
mkdir /opt/software
```

2. Download the version 3.5.7 of ZooKeeper from the Apache website:
```
cd /opt/software/
wget https://archive.apache.org/dist/zookeeper/zookeeper-3.5.7/apache-zookeeper-3.5.7-bin.tar.gz
```

## Step 2: Extract the Archive

Extract the downloaded tarball on each server:
`tar -zxvf apache-zookeeper-3.5.7-bin.tar.gz -C /opt/module/`

## Step 3: Configure ZooKeeper
