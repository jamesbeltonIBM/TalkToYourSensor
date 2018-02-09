# TalkToYourSensor
This repository contains the 2 Node-RED flows and 1 Watson Conversation json file required to complete the excellent 'Talk to your Sensor using the Watson IoT Platform and Conversation services' Recipe on developerWorks by Christophe Lucas BUT using a mySQL database service (such as ClearDB) as opposed to dashDB / DB2 Warehouse.

The link to the original tutorial is:
https://developer.ibm.com/recipes/tutorials/talk-to-your-sensor-using-the-watson-iot-platform-and-conversation-services/

# How to use
If you would rather use mySQL as opposed to dashDB / DB2 Warehouse for your data repository, then use these flows. There are minor differences. First, a function node has been put in the flow which creates a msg.topic that holds the SQL query for mySQL to then execute. Second, since you cannot bind the mySQL service directly to Node-RED, you must provide the orange mySQL nodes with your connection information. Also, you'll need to use mySQL Workbench or similar to create the required tables.  You can find out more about how to do that in my post which is here:
https://developer.ibm.com/dwblog/2018/talking-cleardb-mysql-via-node-red-ibm-cloud/
