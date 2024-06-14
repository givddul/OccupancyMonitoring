# Real-Time Occupancy Monitoring System for University Library

This projects monitors occupancy levels in a library across different floors and zones. This is accieved by placing microcontrollers with ultrasonic sensors at the enterance of each zone and monitor people passing/leaving. This information is sent to a central microcontroller over bluetooth, which keeps track of the current counts of each zone, as well as the total occupancy level in the library. This central microcontroller then forwards the most recent counts to our website over wifi. The occupancy data is stored in a database, which allows for displaying historic data on the website. 

### Zones monitored
- **Zone 1:** First floor
- **Zone 2:** Ground floor
- **Zone 3:** Second and Third floor

### Microcontrollers
- **3 x Raspberry Pi Pico W**<strong> (2 x Ultrasonic sensors each, batteries)</strong>
- **1 x Arduino UNO Rev 4 Wifi**


The web server is a Node.js Express and stores occupancy data in MongoDB.

### Arduino - C++ Code

The `/Microcontrollers/Ardunio` directory contains two versions of the code for the Arduino UNO R4 Wifi, with and without RTOS. Ideally, we wanted the central Arduino microcontroller to utelize freeRTOS, but ran into memory problems when trying to listen to 3 Picos. Therefore, the `ArduinoFreeRTOS.ino` version only communnicates with 2 Pico units, while the non-RTOS `ArduinoCode.ino` code does the complete job, communicating with all 3 Picos.

## 
<img src="OccupancyMonitoringWebsiteDemo.jpg" alt="structure"/>

## 
**Contributers:** Ludvig Svensson & Seif-Alamir Yousef
