# EG4-18KPV-BatteryDetails
These are casual research results for locating generally undisclosed detailed battery data stored in EG4 18KPV inverters. The deliverable is a mapping of modbus registers discovered.

The EG4 monitoring center website (https://monitor.eg4electronics.com/) collects and displays data for their branded inverters and batteries operating in closed loop configuration. Data is polled at about 1 minute intervals using a form of modbus/tcp protocol. Much of the status/operating data displayed can be found in publicly released documents describing the modbus register assignments adopted by the manufacturer (Luxpower). At this time, not all register assignments have been found publicly. Of particular interest are the battery pack-level data.
<img width="975" height="430" alt="image" src="https://github.com/user-attachments/assets/59892eba-4029-47e7-b1a5-6bd0b95a573d" />
These data are present within the inverter registers, but where and how they are formatted may not have been disclosed. The data are useful for pack management and particularly for optimal inter-pack balancing.

This whitepaper describes knowledge developed from a brief examination of communication behavior on a single system. The hope is to facilitate inclusion of this data on private monitoring platforms and aid further work to better complete an understanding of the battery pack-level data.

About the research to date:
Only a single inverter has been examined. Firmware version fAAB-2525. 
A RJ45 communication module is actively monitored by the eg4 monitor server.
Four identical batteries are monitored in a closed-loop configuration by this inverter. The batteries are early EG4 All Weather wall mount models.
FYI-there is another inverter acting as slave sharing these batteries.
Data was collected using wireshark on the local network.

