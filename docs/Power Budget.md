### <a name="_2vz3p7p7ep0x"></a>**Power Budget**
1. **Microcontroller: PIC18F27Q10T-I/ML**
   1. **Voltage:** 3.3V
   1. **Typical Current Consumption:** ~5-20mA (varies by operation mode)
   1. **Max Current Consumption:** ~50mA
1. **MPU-6500 (Gyroscope/Accelerometer)**
   1. **Voltage:** 3.3V
   1. **Typical Current Consumption:** ~3.9mA (active mode)
   1. **Max Current Consumption:** ~10mA
1. **LMR50410Y3FQDBVRQ1 (3.3V Switching Regulator)**
   1. **Efficiency:** ~80-90%
   1. **Input Voltage:** 9V
   1. **Current Draw (assuming ~100mA load):** ~40mA from 9V battery
1. **LED Indicator (Debugging)**
   1. **Voltage:** 3.3V
   1. **Current Consumption:** ~5-10mA (per LED, assuming one active at a time)
1. **Resistors & Passive Components (Negligible Current Draw)**
   1. 4.7kΩ pull-ups (SDA/SCL) → minimal impact
   1. Decoupling capacitors → only transient current impact

|**Component**|**Voltage (V)**|**Current (mA)**|**Power (mW)**|
| :-: | :-: | :-: | :-: |
|**PIC18F27Q10**|3\.3V|20mA (typical)|66mW|
|**MPU-6500**|3\.3V|4mA (typical)|13\.2mW|
|**LMR50410 Regulator**|9V Input|~40mA|360mW|
|**LED (Debugging)**|3\.3V|5mA|16\.5mW|
|**Misc. (I²C Pull-ups, etc.)**|3\.3V|~1mA|~3.3mW|
|**Total Power (at 3.3V Load)**|**3.3V**|**30-40mA**|**~132mW**|
|**Total Power (from 9V Battery)**|**9V**|**~40mA**|**~360mW**|

- **Battery:** 9V source
- **LMR50410 Efficiency:** ~85%
- **Estimated Battery Life:** If using a **9V battery (~500mAh capacity)**
  - **Run Time = (500mAh) / (40mA) = ~12.5 hours** (estimated)
