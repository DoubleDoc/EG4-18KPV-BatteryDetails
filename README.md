# EG4-18KPV-BatteryDetails
These are casual research results for locating generally undisclosed detailed battery data stored in EG4 18KPV inverters. The deliverable is a mapping of modbus registers discovered.

The EG4 monitoring center website (https://monitor.eg4electronics.com/) collects and displays data for their branded inverters and batteries operating in closed loop configuration. Data is polled at about 1 minute intervals using a form of modbus/tcp protocol. Much of the status/operating data displayed can be found in publicly released documents describing the modbus register assignments adopted by the manufacturer (Luxpower). At this time, not all register assignments have been found publicly. Of particular interest are the battery pack-level data.
<img width="975" height="430" alt="image" src="https://github.com/user-attachments/assets/59892eba-4029-47e7-b1a5-6bd0b95a573d" />
These data are present within the inverter registers, but where and how they are formatted may not have been disclosed. The data are useful for pack management and particularly for optimal inter-pack balancing.

This whitepaper describes knowledge developed from a brief examination of communication behavior on a single system. The hope is to facilitate inclusion of this data on private monitoring platforms and aid further work to better complete an understanding of the battery pack-level data.

# About the research to date

Only a single inverter has been examined. Firmware version fAAB-2525. 

A RJ45 communication module is actively monitored by the eg4 monitor server.

Four identical batteries are monitored in a closed-loop configuration by this inverter. The batteries are early EG4 All Weather wall mount models.

FYI-there is another inverter acting as slave sharing these batteries.

Data was collected using wireshark on the local network.

# Input Register Mapping Table

The pack-level data maintained by the inverter is stored in a linear array beginning at IR 5000. 
There are 30 words allocated to each pack. 
The first pack data is at IR5000, the next pack at IR5030, and continuing.

** Reference the 'Reg_Map.xlsx' file for the register map known so far. ** 

# The major constraints to this project have been limited variability and lack of internal system code. 

I have only one battery type, and one inverter model. Likely the data include battery model data, and different firmware versions may generate different data. One expected field is missing - pack temperature. My packs may not have a functioning PCB thermistor.

Without insignts into the BMS design or internal coding, status and alarm indicators are unknwown. There are enough unknown areas in the map for these important signals to locate.

Any and all input will be appreciated and shared.


