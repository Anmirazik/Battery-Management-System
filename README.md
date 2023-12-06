DFUN Battery Management System
======================================

### About

1. Just a simple Nodered flows for reading data from DFUN Battery Management System and publish it to MQTT Broker 
2. I also add flows for reading data from Battery Charge Controller XYL10A where the specification for the communication is (9600,8,n)

#### What you need ?

1. Just a simple compute , it can be raspberry pi or any other types of computer that can run Node-Red , As for me I use raspberry pi since this BMS is located On-Site
2. Ensure that the raspberry pi are in the same network as the BMS otherwise Modbus TCP won't work since it needs to be in the same network
3. Turn on the DFUN Battery Management System
4. Clone this repo
5. Ensure that modbus pallete library is installed https://github.com/BiancoRoyal/node-red-contrib-modbus.git
6. Deploy and thats all

### How It Works ?

1. The Modbus Node will poll the data every 10 seconds
2. Decode the modbus raw data into float datatype and format
3. Add JSON Key on the data 
4. Combine Each of the JSON Key Value Pair into one single object for ease of reading
5. Publish the data to MQTT Broker for further analysis , you can do whatever you want with this data once it reaches MQTT broker
