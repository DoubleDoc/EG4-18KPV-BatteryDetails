# Battery Detailed Data Register Map

Addr: Modbus word index into IR (Input Register) array, base 10

data 16: Hexidecimal data read from register

data 10: Decimal equivalent adjusted for units



| Addr|data 16|data 10|Item                  |Unit     |Range |Note      |
|:---:|------:|------:|:---------------------|:--------|:---: |:---------|
| 5000|0      |       |                      |         |      |unknown   |
| 5001|0      |       |                      |         |      |unknown   |
| 5002|C040   |       |                      |         |      |unknown   |
| 5003|118    |280    |Design Capacity       |ah       |      |*         |
| 5004|239    |56.1   |Charge Voltage        |0.1V     |      |*         |
| 5005|07D0   |200    |Charge Max Ampacity   |0.1amp   |      |verify    |
| 5006|07D0   |200    |Discharge Max Ampacity|0.1amp   |      |Verify    |
| 5007|01C2   |45     |Min Voltage           |0.1V     |      |Verify    |
| 5008|14B3   |52.96  |Present Voltage       |0.01V    |      |*         |
| 5009|FFDD   |-3.5   |Present Current       |0.1amp   |signed|*         |
| 5010|56     |86     |State of Charge       |%        |      |*         |
|     |64     |100    |State of Health       |%        |      |*         |
| 5011|145    |325    |Cycles                |         |      |*         |
| 5012|78     |12     |Max Cell Temperature  |0.1DegC  |      |*         |
| 5013|006E   |11     |Min Cell Temperature  |0.1DegC  |      |*         |
| 5014|0CF1   |3.313  |Max Cell Voltage      |0.001V   |      |*         |
| 5015|0CEF   |3.311  |Min Cell Voltage      |0.001V   |      |*         |
| 5016|3      |3      |Cell Number Max Temp  |         |      |*         |
|     |1      |1      |Cell Number Min Temp  |         |      |*         |
| 5017|3      |3      |Cell Number Max Volts |         |      |*         |
|     |3      |3      |Cell Number Min Volts |         |      |*         |
| 5018|211    |2.17   |Firmware Verision     |0.01     |      |*         |
| 5019|42     |B      |Text Battery Name     |ASCII    |      |*         |
|     |61     |a      |                      |ASCII    |      |*         |
| 5020|74     |t      |                      |ASCII    |      |*         |
|     |74     |t      |                      |ASCII    |      |*         |
| 5021|65     |e      |                      |ASCII    |      |*         |
|     |72     |r      |                      |ASCII    |      |*         |
| 5022|79     |y      |                      |ASCII    |      |*         |
|     |5F     |/_    |                      |ASCII    |      |*         |
| 5023|49     |I      |                      |ASCII    |      |*         |
|     |44     |D      |                      |ASCII    |      |*         |
| 5024|5F     |\_    |                       |ASCII    |      |*         |
|     |30     |0      |                      |ASCII    |      |*         |
| 5025|31     |1      |                      |ASCII    |      |*         |
|     |0      |       |                      |         |      |unknown   |
| 5026|0      |       |                      |         |      |unknown   |
|     |0      |0      |Battery Index (0=first)|        |      |*         |
| 5027|0      |       |                       |        |      |unknown   |
| 5028|0      |       |                       |        |      |unknown   |
| 5029|0      |       |                       |        |      |unknown   |

Data repeats for additional battery packs at IR5030 and increasing.









