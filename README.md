# EG4-18KPV-BatteryDetails
These are casual research results for locating generally undisclosed detailed battery data stored in EG4 18KPV Solar-hybrid inverters. The deliverable is a mapping of modbus registers discovered.

The EG4 monitoring center website (https://monitor.eg4electronics.com/) collects and displays data for their branded inverters and batteries operating in closed loop configuration. Data is polled at about 1 minute intervals using a form of modbus/tcp protocol. Much of the status/operating data displayed can be found in publicly released documents describing the modbus register assignments adopted by the manufacturer (Luxpower). At this time, not all register assignments have been found publicly. Of particular interest are the battery pack-level data.
<img width="975" height="430" alt="image" src="https://github.com/user-attachments/assets/59892eba-4029-47e7-b1a5-6bd0b95a573d" />
These data are present within the inverter registers, but where and how they are formatted may not have been disclosed. The data are useful for pack management and particularly for optimal inter-pack balancing.

This research describes knowledge developed from a brief examination of communication behavior on a single system. The hope is to facilitate incorporation of these data into private monitoring platforms and aid further work to better complete an understanding of the battery pack-level data.

# About the research to date

Only a single inverter has been examined. Firmware version fAAB-2525. 

A RJ45 communication module is actively monitored by the eg4 monitor server.

Four identical batteries are monitored in a closed-loop configuration using EG4 protocol by this inverter. The batteries are early EG4 All Weather wall mount models.

FYI-there is another inverter acting as slave sharing these batteries.

Data were collected using wireshark on the local network.

# Call for Help

Any additional observations or input will be appreciated and shared. Beyond verifying and finishing out these status words, there possibly may be some control functions implemented though HR registers.

# Input Register Mapping Table

The pack-level data maintained by the inverter are stored in a linear array beginning at IR 5000. 
There are 30 words allocated to each pack. 
The first pack data are at IR5000, the next pack at IR5030, and continuing.

__Reference the [Register Map](Reg_Map.md) file for the register assignments known so far__

# Project constrained by limited variability and closed system code

I have only one battery type, and one inverter model. Likely the data include battery model data/identifiers, and different battery firmware versions may generate different data. One expected field is missing - pack temperature. My packs appear to not have functioning PCB thermistors.

Without insignts into the BMS design or internal coding, status and alarm indicators are unknown. There are enough unknown areas within the registers for these important signals to locate. I would expect some cell-level faults, which could be indicated by bits within words. I also expect some pack level status and alarm/fault fields.

# Future/In Process Standards Work

Check out the Sunspec Alliance standardization work. Secrets become public disclosure requirement. Modbus and IEEE-1547 certifications. EG4 noted the 1547 certification in a recent inverter firmware update, but there are alternate communication options and comms are only in a later revision.

Model definitions are the disclosure
https://github.com/sunspec/models
Model 805 most closely matches the data types sought in this research.

Luxpower (claiming for EG4 18KPv-12LV) example of Sunspec Alliance model complete with modbus registers defined: [Luxpower Model](EG4_White_Label_Certificate_Lux_Power_Modbus_for_1547_PICS_SM000043.xlsx) 
This model is not the mapping in released 18KPVs I have scanned, and it does not include the battery data mapped here. This model states it applies to firmware version fA1.0 (or FA1.0).

Software for testing 
https://github.com/sunspec/pysunspec





