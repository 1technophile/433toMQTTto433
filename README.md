# 433toMQTTto433
  This program enables to:  
  - receive MQTT data from a topic and send RF 433Mhz signal corresponding to the received MQTT data  
  - publish MQTT data to a different topic related to received 433Mhz signal



Some usefull commands to test gateway with mosquitto
Subscribe to the subject for data receiption from RF signal
mosquitto_sub -t home/433toMQTT

Send data by MQTT to convert it on RF signal
mosquitto_pub -t home/MQTTto433/ -m 1315153
