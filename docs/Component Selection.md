**1. Microcontroller**

<table>
<colgroup>
<col style="width: 5%" />
<col style="width: 26%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Option</strong></th>
<th><strong>Component</strong></th>
<th><strong>Pros</strong></th>
<th><strong>Cons</strong></th>
</tr>
<tr class="odd">
<th>1.</th>
<th><p>PIC18F27Q10-I/STX</p>
<p><img src="![PICI-STX](https://github.com/user-attachments/assets/de119159-1bb1-4505-a1f9-6ef9e8628619)"
![PICI-STX](https://github.com/user-attachments/assets/64cc54a0-44c4-4e5b-be88-0e0472c8565b)
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $1.36/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/microchip-technology/PIC18F27Q10-I-STX/10187780"><u>Click
Here</u></a></p>
<p><a
href="https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf"><u>Datasheet</u></a></p>
<p>Mfr: Microchip Technology</p></th>
<th><ul>
<li><blockquote>
<p><strong>High-Performance 8-bit MCU</strong> – Optimized for real-time
control applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Multiple Communication Interfaces</strong> – Supports SPI,
I²C, and UART, useful for interfacing with a gyroscope.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Low Power Consumption</strong> – Ideal for battery-operated
systems.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Configurable Logic &amp; Peripherals</strong> – Reduces the
need for external components.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Analog Features</strong> – Includes ADC and comparators,
useful for sensor integration.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Limited Processing Power</strong> – As an 8-bit MCU, it may
struggle with heavy computations.</p>
</blockquote></li>
<li><blockquote>
<p><strong>No Floating-Point Unit</strong> – Could make complex math
operations slower.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Limited RAM (3.8 KB)</strong> – Might be restrictive for
data-heavy applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Through-Hole Package (DIP-28)</strong> – Good for
prototyping, but may not be ideal for compact designs.</p>
</blockquote></li>
</ul></th>
</tr>
<tr class="header">
<th>2.</th>
<th><p>PIC18F46Q71-I/P</p>
<p><img src="media/image1.png"
style="width:1.5625in;height:0.69792in" /></p>
<p>Price: $2.43/unit</p>
<p>Link: <a
href="https://www.mouser.com/ProductDetail/Microchip-Technology/PIC18F46Q71-I-P?qs=8Wlm6%252BaMh8QSpCj2xCNqDg%3D%3D"><u>Click
Here</u></a></p>
<p><a
href="https://www.mouser.com/datasheet/2/268/PIC18F26_46_56Q71_Microcontroller_Data_Sheet_DS400-3314555.pdf"><u>Datasheet</u></a></p>
<p>Mfr: Microchip Technology</p></th>
<th><ul>
<li><blockquote>
<p><strong>More Processing Power</strong> – 8-bit MCU but with a higher
feature set than standard PIC18s.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Dedicated Math Accelerator</strong> – Helps with DSP-like
operations, useful for sensor fusion.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Multiple Communication Interfaces</strong> – SPI, I²C, and
UART for seamless gyroscope integration.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Advanced Analog Features</strong> – 12-bit ADC, op-amps, and
DAC, improving sensor signal handling.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Extended Temperature Range</strong> – Good for industrial
applications.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Larger Package (DIP-40)</strong> – Takes up more PCB space,
which may not be ideal for compact designs.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Still 8-bit</strong> – Might be limiting for high-speed or
complex real-time processing.</p>
</blockquote></li>
<li><blockquote>
<p><strong>No Floating-Point Support</strong> – Can slow down complex
calculations.</p>
</blockquote></li>
</ul></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

I chose the PIC18F27Q10 because it provides the necessary communication
interfaces (SPI, I²C, UART) for gyroscope data collection, has low power
consumption, and includes configurable peripherals that simplify
integration. Additionally, it was already available in class, making it
a more convenient and cost-effective choice.

**2. Gyroscope**

<table>
<colgroup>
<col style="width: 5%" />
<col style="width: 26%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Option</strong></th>
<th><strong>Component</strong></th>
<th><strong>Pros</strong></th>
<th><strong>Cons</strong></th>
</tr>
<tr class="odd">
<th>1.</th>
<th><p>MPU-6050</p>
<p><img src="media/image2.png"
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $13.95/unit</p>
<p>Link: <a
href="https://www.sparkfun.com/3-axis-gyro-accelerometer-ic-mpu-6050.html?gQT=1"><u>Click
Here</u></a></p>
<p><a
href="https://cdn.sparkfun.com/datasheets/Components/General%20IC/PS-MPU-6000A.pdf"><u>Datasheet</u></a></p>
<p>Mfr: InvenSense</p></th>
<th><ul>
<li><blockquote>
<p><strong>3.3V Compatible</strong> – Works with desired power
setup.</p>
</blockquote></li>
<li><blockquote>
<p><strong>I²C Communication</strong> – Simple two-wire interface.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Built-in Accelerometer &amp; Gyroscope</strong> – Provides
6DOF motion tracking.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Digital Motion Processor (DMP)</strong> – Offloads sensor
fusion calculations from the MCU.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Low Power Consumption</strong> – Suitable for battery-powered
applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Well-Supported in MicroPython</strong> – Libraries available
for easy integration.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>No Magnetometer</strong> – Cannot determine absolute
orientation without an external sensor.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Can Be Noisy</strong> – Requires filtering for precise
readings.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Factory Calibration May Vary</strong> – Might need additional
software calibration.</p>
</blockquote></li>
</ul></th>
</tr>
<tr class="header">
<th>2.</th>
<th><p>A3G4250DTR</p>
<p><img src="media/image11.png"
style="width:1.5625in;height:1.5625in" /></p>
<p>Price: $15.66/unit</p>
<p>Link: <a
href="https://www.mouser.com/ProductDetail/STMicroelectronics/A3G4250DTR?qs=Ld7sMN6XJzCU8%252BkHd1RE7g%3D%3D&amp;mgh=1&amp;gQT=1"><u>Click
Here</u></a></p>
<p><a
href="https://www.mouser.com/datasheet/2/389/a3g4250d-1849040.pdf"><u>Datasheet</u></a></p>
<p>Mfr: STMicroelectronics</p></th>
<th><ul>
<li><blockquote>
<p><strong>3.3V Operation</strong> – Directly compatible with desired
power supply.</p>
</blockquote></li>
<li><blockquote>
<p><strong>I²C &amp; SPI Support</strong> – Flexible communication
options.</p>
</blockquote></li>
<li><blockquote>
<p><strong>High-Resolution (16-bit output)</strong> – Provides precise
angular rate data.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Low Power Consumption</strong> – Suitable for
battery-operated applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Embedded Low-Pass Filter</strong> – Helps reduce noise in
measurements.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>No Accelerometer or Magnetometer</strong> – Only provides
gyroscope data.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Limited Community Support</strong> – Fewer MicroPython
libraries available.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Fixed Full-Scale Range (±245 dps)</strong> – Not adjustable
for higher-speed motion tracking.</p>
</blockquote></li>
</ul></th>
</tr>
<tr class="odd">
<th>3.</th>
<th><p>ICM-20948</p>
<p><img src="media/image6.png"
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $7.11/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/tdk-invensense/ICM-20948/7062698"><u>Click
Here</u></a></p>
<p><a
href="http://www.invensense.com/wp-content/uploads/2016/06/DS-000189-ICM-20948-v1.3.pdf"><u>Datasheet</u></a></p>
<p>Mfr: TDK InvenSense</p></th>
<th><ul>
<li><blockquote>
<p><strong>9-DOF Sensor:</strong> Includes a <strong>3-axis gyroscope,
3-axis accelerometer, and 3-axis magnetometer</strong> for comprehensive
motion sensing.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Low Power Consumption:</strong> Optimized for battery-powered
applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>I2C &amp; SPI Support:</strong> Provides flexibility in
communication options.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Built-in DMP (Digital Motion Processor):</strong> Offloads
sensor fusion and calculations from the microcontroller.</p>
</blockquote></li>
<li><blockquote>
<p><strong>High Sensitivity:</strong> Precise motion tracking with
<strong>±2000 dps gyroscope, ±16g accelerometer, and ±4900µT
magnetometer</strong>.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Small Form Factor:</strong> Suitable for compact embedded
systems.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Complex Configuration:</strong> Requires multiple
initialization steps and careful register management.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Limited 3.3V Compatibility:</strong> Needs <strong>level
shifting</strong> if interfacing with <strong>5V
microcontrollers</strong>.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Magnetometer Requires Extra Handling:</strong> Uses an
<strong>AK09916</strong> chip internally, requiring separate I2C
communication.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Higher Cost:</strong> More expensive than simpler IMUs like
the <strong>MPU6050</strong>.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Limited Library Support in MicroPython:</strong> Might
require custom driver development for full functionality.</p>
</blockquote></li>
</ul></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

I chose the MPU-6050 over the others because it includes both a
gyroscope and accelerometer, providing 6DOF motion tracking, whereas the
A3G4250DTR only offers gyroscope data. The MPU-6050 has better
MicroPython support, making integration easier, and operates at 3.3V
with I²C, aligning well with my system's power and communication setup.

**3. Voltage Regulator**

<table>
<colgroup>
<col style="width: 5%" />
<col style="width: 26%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Option</strong></th>
<th><strong>Component</strong></th>
<th><strong>Pros</strong></th>
<th><strong>Cons</strong></th>
</tr>
<tr class="odd">
<th>1.</th>
<th><p>LM2675MX-3.3/NOPB</p>
<p><img src="media/image7.png"
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $4.36/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/texas-instruments/LM2675MX-3-3-NOPB/366907"><u>Click
Here</u></a></p>
<p><a
href="https://www.ti.com/general/docs/suppproductinfo.tsp?distId=10&amp;gotoUrl=https%3A%2F%2Fwww.ti.com%2Flit%2Fgpn%2Flm2675"><u>Datasheet</u></a></p>
<p>Mfr: Texas Instruments</p></th>
<th><ul>
<li><blockquote>
<p><strong>Switching Regulator (Buck Converter)</strong> – Higher
efficiency than linear regulators.</p>
</blockquote></li>
<li><blockquote>
<p><strong>3.3V Fixed Output</strong> – No need for external voltage
adjustment.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Wide Input Voltage Range (6.5V–40V)</strong> – Compatible
with a 9V battery.</p>
</blockquote></li>
<li><blockquote>
<p><strong>High Efficiency (~90%)</strong> – Reduces heat and extends
battery life.</p>
</blockquote></li>
<li><blockquote>
<p><strong>500mA Output Current</strong> – Sufficient for low-power
microcontroller systems.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Built-in Thermal Shutdown and Current Limiting</strong> –
Protects against overheating and overcurrent.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Requires External Inductor and Capacitors</strong> – More
complex circuit design.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Larger Footprint than AMS1117</strong> – Takes up more PCB
space.</p>
</blockquote></li>
<li><blockquote>
<p><strong>More Expensive than Linear Regulators</strong> – Higher cost
per unit.</p>
</blockquote></li>
</ul></th>
</tr>
<tr class="header">
<th>2.</th>
<th><p>AMS1117-3.3S</p>
<p><img src="media/image8.png"
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $0.47/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/evvo/AMS1117-3-3S/24370078"><u>Click
Here</u></a></p>
<p><a
href="https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/6283/AMS1117-3.3S.pdf"><u>Datasheet</u></a></p>
<p>Mfr: EVVO</p></th>
<th><ul>
<li><blockquote>
<p><strong>3.3V Fixed Output</strong> – Stable voltage for
microcontrollers and sensors.</p>
</blockquote></li>
<li><blockquote>
<p><strong>800mA Maximum Output Current</strong> – Sufficient for
low-power embedded systems.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Compact SOT-223 Package</strong> – Saves PCB space.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Simple Implementation</strong> – Requires minimal external
components (capacitors for stability).</p>
</blockquote></li>
<li><blockquote>
<p><strong>Low Cost</strong> – Affordable for most applications.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Linear Regulator (Low Efficiency)</strong> – Converts excess
power into heat, reducing battery life.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Requires Heat Dissipation</strong> – May need a heat sink at
higher loads.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Higher Power Loss Compared to Switching Regulators</strong> –
Not ideal for energy-efficient designs.</p>
</blockquote></li>
</ul></th>
</tr>
<tr class="odd">
<th>3.</th>
<th><p>AMS1117-3.3</p>
<p><img src="media/image5.png"
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $0.68/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/umw/AMS1117-3-3/17635254"><u>Click
Here</u></a></p>
<p><a
href="https://mm.digikey.com/Volume0/opasdata/d220001/medias/docus/5011/AMS1117.pdf"><u>Datasheet</u></a></p>
<p>Mfr: UMW</p></th>
<th><ul>
<li><blockquote>
<p><strong>Low Dropout Voltage:</strong> Requires only
<strong>1.1V</strong> difference between input and output, making it
efficient for regulating <strong>9V down to 3.3V</strong>.</p>
</blockquote></li>
<li><blockquote>
<p><strong>3.3V Fixed Output:</strong> Perfect for powering
<strong>low-voltage microcontrollers and sensors</strong> like the
<strong>PIC18F27Q10</strong> and <strong>MPU6050</strong>.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Simple Design:</strong> Only requires a few capacitors for
stability.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Compact Size:</strong> Available in <strong>SOT-223
package</strong>, ideal for PCB designs.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Affordable &amp; Widely Available:</strong> Low-cost voltage
regulation solution.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Low Current Output:</strong> Maximum <strong>800mA</strong>,
which may be insufficient for power-hungry peripherals.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Linear Regulator Efficiency:</strong> Wastes excess energy as
heat, especially when stepping down from <strong>9V to
3.3V</strong>.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Requires Heat Dissipation:</strong> Can overheat if powering
multiple components without a heatsink.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Not the Best for Battery-Powered Applications:</strong>
Inefficient compared to <strong>switching regulators (buck
converters)</strong>.</p>
</blockquote></li>
</ul></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

The AMS1117-3.3S was chosen over the others because it is simpler to
implement, requires fewer external components, and is more compact and
cost-effective for the system's power needs. While it has lower
efficiency, heat dissipation is manageable given the system's power
requirements.

**4. Power Supply**

<table>
<colgroup>
<col style="width: 5%" />
<col style="width: 26%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>Option</strong></th>
<th><strong>Component</strong></th>
<th><strong>Pros</strong></th>
<th><strong>Cons</strong></th>
</tr>
<tr class="odd">
<th>1.</th>
<th><p>B0B248DSFG</p>
<p><img src="media/image10.png"
style="width:1.5625in;height:1.29167in" /></p>
<p>Price: $11.98</p>
<p>Link: <a
href="https://www.amazon.com/PAISUE-Rechargeable-Lithium-ion-Multimeter-Microphone/dp/B0B248DSFG?source=ps-sl-shoppingads-lpcontext&amp;ref_=fplfs&amp;smid=A2WEVNKRB72JGE&amp;gQT=1&amp;th=1"><u>Click
Here</u></a></p>
<p><a href="https://a.co/d/bxvgbKX"><u>Datasheet</u></a></p>
<p>Mfr: LCLEBM</p></th>
<th><ul>
<li><blockquote>
<p><strong>9V, 1500mAh Capacity</strong> – Provides decent runtime for
low-power applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Rechargeable Li-ion Chemistry</strong> – Reduces waste and
long-term costs.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Built-in Protection Circuit</strong> – Prevents overcharging,
over-discharging, and short circuits.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Compact Size</strong> – Fits standard 9V battery holders.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Actual Capacity May Be Lower Than Advertised</strong> – Some
9V Li-ion batteries have lower true capacity.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Voltage Drops Under Load</strong> – May affect performance in
high-current applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Requires a Compatible Charger</strong> – Cannot be charged
with a standard NiMH or alkaline charger.</p>
</blockquote></li>
</ul></th>
</tr>
<tr class="header">
<th>2.</th>
<th><p>3046-9V-ND</p>
<p><img src="media/image4.png"
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $4.46/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/duracell-industrial-operations-inc/9V/21259959"><u>Click
Here</u></a></p>
<p><a
href="https://www.duracell.com/wp-content/uploads/2016/03/MN1604_US_CT1.pdf"><u>Datasheet</u></a></p>
<p>Mfr: Duracell</p></th>
<th><ul>
<li><blockquote>
<p><strong>Reliable Duracell Brand</strong> – Known for consistent
quality and performance.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Alkaline Chemistry</strong> – Provides stable voltage for
moderate-power applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>No Recharge Required</strong> – Convenient for one-time use
scenarios.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Long Shelf Life</strong> – Retains charge well when
stored.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Non-Rechargeable</strong> – Increases long-term cost and
waste.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Lower Capacity Than Li-ion</strong> – Drains faster under
high loads.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Voltage Drops Over Time</strong> – Performance degrades as
the battery discharges.</p>
</blockquote></li>
</ul></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

The B0B248DSFG (9V Li-ion) was chosen over the Duracell 9V (alkaline)
because it is rechargeable, offers a higher capacity, and maintains a
more stable voltage under load, making it more cost-effective and
efficient for long-term use in the system.

**Microcontroller Selection:**

### **1. Determine Project-Specific Requirements** {#determine-project-specific-requirements}

- **Communication Protocols:**

  - **SPI**: Likely needed for high-speed data transfer (check gyroscope
    > requirements).

  - **I2C**: Used for lower-speed sensors (MPU-6050 uses I2C).

  - **UART**: Might be needed for debugging or interfacing with other
    > systems.

- **Pin Requirements:**

  - **Power & Ground**: At least 2 pins.

  - **Programming**: 1 pin for ICSP (for the PIC).

  - **GPIO**: Additional for controlling/resetting components.

  - **Communication**: I2C (SCL, SDA), SPI (MISO, MOSI, SCK, SS), and
    > possibly UART.

### **2. Researching the PIC18F27Q10 Microcontroller** {#researching-the-pic18f27q10-microcontroller}

| **Feature**       | **PIC18F27Q10**                  |
|-------------------|----------------------------------|
| Pins              | 28                               |
| I2C               | 2 modules                        |
| SPI               | 2 modules                        |
| UART              | 2 modules                        |
| GPIO              | 25 (shared with other functions) |
| Operating Voltage | 3.3V or 5V                       |
| Flash Memory      | 128 KB                           |
| RAM               | 8 KB                             |
| EEPROM            | 1 KB                             |
| Clock Speed       | 64 MHz                           |

- **Meets Requirements**:

  - Supports I2C (needed for MPU-6050)

  - Has enough GPIOs for additional connections

  - Multiple communication protocols (SPI, UART, etc.)

- **Exceeds Requirements**:

  - Extra memory and processing power beyond the immediate need.

- **Does Not Meet Requirements**:

  - No built-in WiFi/Bluetooth (handled by the ESP32 on another team
    > member's end).

### **3. Checking for Compatibility Issues:** {#checking-for-compatibility-issues}

- The MPU-6050 gyroscope is commonly used with the PIC18F27Q10, but Microchip libraries and drivers should be verified.

- Check if Microchip\'s I2C library supports MPU-6050 well.

- Look for existing libraries for interfacing the MPU-6050 with PIC (Microchip Harmony, MPLAB Code Configurator, etc.)

- Ensure no known I2C clock stretching issues with PIC.

### **4. Role Description** {#role-description}

As part of Team 309, the responsibility is to interface the MPU-6050
gyroscope with the PIC18F27Q10 to measure the rotation speed of the
spinning top\'s motor. This data will then be transmitted to another
team member's ESP32, which will handle further communication with the
human interface module for visualization.

**Key Responsibilities:**

- **Sensing**: Capturing rotational data via MPU-6050 (I2C).

- **Processing**: Sending processed data from PIC18F27Q10 to ESP32.

- **Power Management**: Ensuring compatibility with 3.3V power supply.

- **Communication**: Handling I2C communication between the PIC and MPU-6050.

### **PIC Table**

| **ESP Info**                                 | **Answer**                                                                                                                         |
|----------------------------------------------|------------------------------------------------------------------------------------------------------------------------------------|
| **Model**                                    | PIC18F27Q10                                                                                                                        |
| **Product Page URL**                         | [[Microchip Product Page]{.underline}](https://www.digikey.com/en/products/detail/microchip-technology/PIC18F27Q10-I-STX/10187780) |
| **Datasheet URL(s)**                         | [[Datasheet]{.underline}](https://ww1.microchip.com/downloads/en/DeviceDoc/PIC18F27-47Q10-Data-Sheet-40002043E.pdf)                |
| **Application Notes URL(s)**                 | [[Application Notes]{.underline}](https://www.microchip.com/en-us/application-notes)                                               |
| **Vendor link**                              | [[DigiKey]{.underline}](https://www.digikey.com/)                                                                                  |
| **Code Examples**                            | [[Microchip GitHub]{.underline}](https://github.com/Microchip-MPLAB-Harmony)                                                       |
| **External Resources URL(s)**                | [[YouTube]{.underline}](https://www.youtube.com/watch?v=CfWcoWoPKDs)                                                               |
| **Unit cost**                                | \$2.08                                                                                                                             |
| **Absolute Maximum Current for entire IC**   | 250mA                                                                                                                              |
| **Supply Voltage Range**                     | 2.3V (Min) / 3.3V or 5V (Nominal) / 5.5V (Max)                                                                                     |
| **Absolute Maximum Current (for entire IC)** | 250mA                                                                                                                              |
| **Maximum GPIO current (per pin)**           | 25mA                                                                                                                               |
| **Supports External Interrupts?**            | Yes                                                                                                                                |
| **Required Programming Hardware, Cost, URL** | None                                                                                                                               |
| **Works with MPLabX?**                       | Yes                                                                                                                                |
| **Works with Microchip Code Configurator?**  | Yes                                                                                                                                |

### **Available Modules & Pin Assignments** {#available-modules-pin-assignments}

| **Module** | **\# Available** | **Needed** | **Associated Pins (or \* for any)** |
|------------|------------------|------------|-------------------------------------|
| **GPIO**   | 25               | 4          | \*                                  |
| **ADC**    | 11               | 0          | N/A                                 |
| **UART**   | 2                | 1          | TX, RX                              |
| **SPI**    | 2                | 1          | SCK, MISO, MOSI, SS                 |
| **I2C**    | 2                | 1          | SDA, SCL                            |
| **PWM**    | 7                | 0          | N/A                                 |
| **ICSP**   | 1                | 1          | PGD, PGC, MCLR                      |

### **Power Supply & Voltage Regulation Considerations:** {#power-supply-voltage-regulation-considerations}

- **9V battery** → AMS1117-3.3S (Regulates down to 3.3V for PIC & MPU6050)

- **AMS1117-3.3S Connections:**

  - Vin → 9V Battery

  - Vout → PIC18F27Q10 (VDD) & MPU6050 (VCC)

  - GND → Common ground

### **Peripheral Breakdown:**

- **MPU6050 Gyroscope (I2C Interface)**

  - SCL → RC3 (Pin 18)

  - SDA → RC4 (Pin 23)

  - VCC → 3.3V (From AMS1117)

  - GND → Common Ground

  - INT (Optional) → Assign to an available GPIO if needed

- **Voltage Regulator (AMS1117-3.3S)**

  - Vin → 9V Battery

  - Vout → 3.3V for PIC & MPU6050

  - GND → Common Ground

MPLABX MCC Screenshot:

![](media/image9.png){width="3.0061581364829397in"
height="1.7552088801399826in"}
