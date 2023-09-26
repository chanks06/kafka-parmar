# kafka-parmar
Data Engineering project outlined by Darshil Parmar 

[Stock Market Real-Time Data Analysis Using Kafka | End-To-End Data Engineering Project](https://www.youtube.com/watch?v=KerNf0NANMo)

What is Kafka ? 
Apache Kafka is a distributed event store and stream-procesing platform. 

What is event streaming ? 
Event streaming is the practice of capturing data in real-time from event sources like databases, sensors, mobile devices, cloud services, and software applications in the form of streams of events; storing these event streams durably for later retrieval; manipulating, processing, and reacting to the event streams in real-time as well as retrospectively; and routing the event streams to different destination technologies as needed. Event streaming thus ensures a continuous flow and interpretation of data so that the right information is at the right place, at the right time. (https://kafka.apache.org/intro)

PREREQUISTES 
1. Create AWS account
2. Create EC2 instance
3. Connect to instance from personal machine via ssh:

Commands for Setting up virtual machine (bash):  

-- connecting to VM via ssh 
$ ssh -i "kafka-stock-market-project.pem" ec2-user@ec2-3-138-186-180.us-east-2.compute.amazonaws.com

-- downloading compressed verson of apache kafka 
$ wget https://downloads.apache.org/kafka/3.5.1/kafka_2.12-3.5.1.tgz

-- extracting compressed kafka
$ tar -xvf kafka_2.12-3.5.1.tgz

--installing java 
$ sudo yum install java-devel

--check java version installed on vm
$ java -version 

 -- start zookeeper 
 $ bin/zookeeper-server-start.sh config/zookeeper.properties

 OPEN NEW COMMAND LINE WINDOW (we are keeping zookeeper running in other window) 
-- Start kafka-server: navigate to folder with key and connect to ec2 machine
$ ssh -i "kafka-stock-market-project.pem" ec2-user@ec2-3-138-186-180.us-east-2.compute.amazonaws.com

--change memory (I don't know) 
$ export KAFKA_HEAP_OPTS="-Xmx256M -Xms128M"

--start kafka 
$ bin/kafka-server-start.sh config/server.properties

--changing host of config/server.properties to ec2 public ip address
$ sudo nano config/server.properties


