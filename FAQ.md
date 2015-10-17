---
layout: doc
title:  "Frequently Asked Questions"
permalink: /docs/FAQ.html
---

* **Q1. Not able to access storm worker log via browser**

	> Add the following line in host machine's hosts file

      127.0.0.1 sandbox.hortonworks.com

* **Q2. Not able send data into kafka using kafka console producer**: 

	  /usr/hdp/current/kafka-broker/bin/kafka-console-producer.sh --broker-list localhost:6667 --topic sandbox_hdfs_audit_log

	> Kafka broker are binding to host sandbox.hortonworks.com

      $ /usr/hdp/current/kafka-broker/bin/kafka-console-producer.sh --broker-list sandbox.hortonworks.com:6667 --topic sandbox_hdfs_audit_log
      $ cat /etc/hosts
      127.0.0.1 localhost.localdomain localhost
      10.0.2.15 sandbox.hortonworks.com sandbox ambari.hortonworks.com

* **Q3. Cannot visit eagle service url http://localhost:9099 through the browser**

	> If your network is NAT, then you need to add forwarding port 9099 for eagle service, or you should check if HBase is alive.

* **Q4: There is no data in Kafka topic after installing log4j Kafka appender**
	
	> There are a few reasons for this: 1) check if the log4j kafka appender is installed successfully and there is no exceptions when restarting the namenode. 2) check if Kafka is started. 3) If everything is ok, the final choice is to restart the namenode again.
 	

* **Q5: There is no workers in some topology.**

	> Storm in sandbox has only two slots (workers) to run topologies by default. If want to run more than two topologies, a user should add extra slots in the
configurations and restart Storm
	![Add slots](/images/docs/stormConf.png)



