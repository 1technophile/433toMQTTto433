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

Tested with the following libraries versions:
Ethernet version 1.1.2
pubsubclient version 2.6

A list of supported 433mhz devices is available here:
https://community.home-assistant.io/t/433tomqttto433-gateway-device-list/7819


Permission is hereby granted, free of charge, to any person obtaining a copy of this software 
and associated documentation files (the "Software"), to deal in the Software without restriction, 
including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, 
and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, 
subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED 
TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL 
THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF 
CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
