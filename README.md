# Installation and configuration of ZooKeeper for [Spark real-time project](https://github.com/PetitPoissonL/Spark_Streaming_Real_Time)
This guide provides detailed steps to install and configure Apache ZooKeeper on a cluster of three servers: `hadoop102`, `hadoop103`, and `hadoop104`. ZooKeeper is a high-performance coordination service for distributed applications.

## Prerequisites

Ensure the following prerequisites are met on all three servers:

- Linux-based environment (CentOS 7.5)
- Java JDK installed (version 1.8.0_212)
- Cluster distribution script [xsync](https://github.com/PetitPoissonL/Cluster-distribution-script-xsync/tree/main)
- Network connectivity between all three servers
- Sufficient permissions to install and configure software

## Step 1: Download ZooKeeper

Perform the following steps on the server `hadoop102`:

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
```
tar -zxvf apache-zookeeper-3.5.7-bin.tar.gz -C /opt/module/
```

Rename 'apache-zookeeper-3.5.7-bin' to 'zookeeper-3.5.7':
```
cd /opt/module/
mv apache-zookeeper-3.5.7-bin/ zookeeper-3.5.7
```

## Step 3: Configure ZooKeeper
1. Configure the server number:
Create 'zkData' directory under the '/opt/module/zookeeper-3.5.7/' directory
```
mkdir zkData
```
2. Create a file named 'myid' in the '/opt/module/zookeeper-3.5.7/zkData' directory:
```
vim myid
```
3. Add the corresponding number for the server in the file (Note: No empty lines above or below, no spaces on the left or right):
```
2
```
4. Copy the configured ZooKeeper to other machines:
```
xsync zookeeper-3.5.7
```
And modify the content in the 'myid' file to '3' on `hadoop103` and '4' on `hadoop104`, respectively
