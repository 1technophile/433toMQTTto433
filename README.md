# 433toMQTTto433
  This program enables to:  
  - receive MQTT data from a topic and send RF 433Mhz signal corresponding to the received MQTT data  
  - publish MQTT data to a different topic related to received 433Mhz signal

Transmitter VCC must be plugged to pin 9, signal to pin 10
Receiver signal to pin 2

More info on http://1technophile.blogspot.fr/2016/04/433tomqttto433-bidirectional-gateway.html

Some usefull commands to test gateway with mosquitto
Subscribe to the subject for data receiption from RF signal
mosquitto_sub -t home/433toMQTT

Send data by MQTT to convert it on RF signal
mosquitto_pub -t home/MQTTto433/ -m 1315153

*IMPORTANT NOTE:* As described on the blog post cited above, this setup uses an output pin to drive the RF transciever's Vcc and assumes/requires that your transciever can handle the full 5V that most Arduino output pins deliver.  Using this setup against a transciever built for 3.3V (e.g., RF1100SE/CC110) without a level shifter or other voltage reducer will potentially overload and destroy your transceiver.
