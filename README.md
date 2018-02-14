# TalkToYourSensor
This repository contains the 2 Node-RED flows and 1 Watson Conversation json file required to complete the excellent 'Talk to your Sensor using the Watson IoT Platform and Conversation services' Recipe on developerWorks by Christophe Lucas BUT using a mySQL database service (such as ClearDB) as opposed to dashDB / DB2 Warehouse. This version also includes Watson Text to Speech integration meaning that the chatbot will speak it's responses back to you and when you are actively uploading sensor data, if the light reading is over 80 lux (shine a bright light / torch at it) an audiable Warning! will sound (note you will need to have the flow editor open to hear both the chat and the warning).

The link to the original tutorial is:
https://developer.ibm.com/recipes/tutorials/talk-to-your-sensor-using-the-watson-iot-platform-and-conversation-services/

# How to use
If you would rather use mySQL as opposed to dashDB / DB2 Warehouse for your data repository, then use these flows. There are minor differences. First, a function node has been put in the flow which creates a msg.topic that holds the SQL query for mySQL to then execute. Second, since you cannot bind the mySQL service directly to Node-RED, you must provide the orange mySQL nodes with your connection information. Also, you'll need to use mySQL Workbench or similar to create the required tables.  You can find out more about how to do that in my post which is here:
https://developer.ibm.com/dwblog/2018/talking-cleardb-mysql-via-node-red-ibm-cloud/

To use the Watson text to speech elements, you need to create a text to speech service and connect it to your Node-Red service (or open the text to speech node and add in your service credentials if you don't want to connect them). 
You will also need to install the Audio node into your Node-RED pallette. Do this by clicking the hamburger (three horizontal lines to the right of the Deploy button on the editor), then click Manage Pallette and on the Install tab, type 'audio' into the search bar and then look for 'node-red-contrib-play-audio'. Click install beside this to install.

The audio will only play through your computer speakers when the Node-Red editor is open. 
