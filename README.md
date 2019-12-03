# PILS-LoRa

This repository contains the main files to establish a LoRa link between a RPI and a distant server.

# TTN platform
1) Clone the lmic_pi-master repository
2) Open the examples/thethingsnetwork-send-v1/thethingsnetwork-send-v1.cpp file
3) Go to the TTN application (id: pils-connect-v1) and copy the device ID, Network Session Key and App Session key to the file
4) Run the commands:
  - make
  - sudo ./thethingsnetwork-send-v1
  
5) Check the reception of packets on TTN interface

# Adaptative Data Rate protocol (ADR)
Easy way: enable the ADR mode on the RPi: LMIC_setAdrMode(1). TTN will automatically enable the ADR protocol as the ADR bit is set to 1.

Not-so-easy way: implement ADR by yourself (see https://www.linuxembedded.fr/2017/12/introduction-a-lora/). Useful function: LMIC_setLinkCheckMode(1), which will enable TTN to send ACKs.
