# Dual MQTT Brokers on ESP32
This code performs data publishing and subcribing on two MQTT Brokers simultaneously

## GPIO Functions:
I am using ENC28J60 Ethernet Module and Devkit v1's integrated Wifi.
* GPIO 18 : SCLK 
* GPIO 23 : MOSI
* GPIO 19 : MISO
* GPIO 5  : CS
* SPI CLOCK MHz : 8MHz
* **NOTE : SDK Configurations for SPI has to be done on individual level**

## Understanding the Flow:
* This code is developed for ESP32 on Embedded C Language using FreeRTOS.
* MQTT is a lightweight, publish-subscribe network protocol that transports messages between devices. The protocol usually runs over TCP/IP.
* ESP32 will the client and the MQTT URL will be the Broker.
* A client can either subscribe to a specific topic on the MQTT broker and get the data/messages.
* Client can also publish to a specific topic on the MQTT broker
* In this example, I will connect to two separate MQTT Brokers from same ESP32 and create both subscribing and publishing logic.
* I am pinging "www.google.com" to verify Internet Services but you can also ping the MQTT broker itself ( which is much more optimal solution ).

## Conclusion:
* Turns out, you can connect to multiple MQTT Brokers at the same time, but stability/reliablity is still not confirmed.
* **VERY IMPORTANT: ESP gives WIFI connection priority over Ethernet by default ( at least in my test cases ). Hence, if your ESP is connected to an AP but isn't receiving any Internet Packages, it won't shift to Ethernet!!**
