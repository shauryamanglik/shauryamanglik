**EGR314: Component Selection**

**Shaurya Manglik**

1.  **Microcontroller**

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
<th><p>PIC18F27Q10-I/SP</p>
<p><img src="media/image2.png"
style="width:1.55208in;height:1.55556in" /></p>
<p>Price: $2.08/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/microchip-technology/PIC18F27Q10-I-SP/10187778"><u>Click
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

2.  **Gyroscope**

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
<p><img src="media/image5.png"
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
<p><img src="media/image3.png"
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
</thead>
<tbody>
</tbody>
</table>

I chose the MPU-6050 over the A3G4250DTR because it includes both a
gyroscope and accelerometer, providing 6DOF motion tracking, whereas the
A3G only offers gyroscope data. The MPU-6050 has better MicroPython
support, making integration easier, and operates at 3.3V with I²C,
aligning well with my system's power and communication setup.

3.  **ESP32**

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
<th><p>ESP32-S3-WROOM-1-N4</p>
<p><img src="media/image6.png"
style="width:1.5625in;height:1.56944in" /></p>
<p>Price: $2.95/unit</p>
<p>Link: <a
href="https://www.digikey.com/en/products/detail/espressif-systems/ESP32-S3-WROOM-1-N4/16162639"><u>Click
Here</u></a></p>
<p><a
href="https://www.espressif.com/sites/default/files/documentation/esp32-s3-wroom-1_wroom-1u_datasheet_en.pdf"><u>Datasheet</u></a></p>
<p>Mfr: Espressif Systems</p></th>
<th><ul>
<li><blockquote>
<p><strong>Powerful Dual-Core Processor</strong> – Handles complex
computations efficiently.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Wi-Fi &amp; Bluetooth 5.0</strong> – Enables wireless
communication and IoT applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Supports MicroPython</strong> – Well-documented libraries
available.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Multiple I/O Interfaces</strong> – SPI, I²C, UART, PWM, ADC,
and DAC.</p>
</blockquote></li>
<li><blockquote>
<p><strong>3.3V Logic Level</strong> – Compatible with your power
setup.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Large Flash Storage (4MB)</strong> – Allows for extensive
firmware and data storage.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Higher Power Consumption</strong> – Uses more power than
basic microcontrollers.</p>
</blockquote></li>
<li><blockquote>
<p><strong>3.3V Logic Only</strong> – Requires level shifting if
interfacing with 5V components.</p>
</blockquote></li>
<li><blockquote>
<p><strong>No Native USB-to-Serial Converter</strong> – Needs an
external chip or board for easier programming.</p>
</blockquote></li>
</ul></th>
</tr>
<tr class="header">
<th>2.</th>
<th><p>ESP32-WROOM-32UE-N4</p>
<p><img src="media/image4.png"
style="width:1.5625in;height:1.5625in" /></p>
<p>Price: $2.50/unit</p>
<p>Link: <a
href="https://www.mouser.com/ProductDetail/Espressif-Systems/ESP32-WROOM-32UE-N4?qs=Li%252BoUPsLEnsnnWrvUBU2ZA%3D%3D"><u>Click
Here</u></a></p>
<p><a
href="https://www.mouser.com/datasheet/2/891/esp32_wroom_32e_esp32_wroom_32ue_datasheet_en-1855879.pdf"><u>Datasheet</u></a></p>
<p>Mfr: Espressif Systems</p></th>
<th><ul>
<li><blockquote>
<p><strong>Dual-Core Processor</strong> – Handles multitasking and
real-time processing efficiently.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Wi-Fi &amp; Bluetooth 4.2</strong> – Supports wireless
communication for IoT applications.</p>
</blockquote></li>
<li><blockquote>
<p><strong>MicroPython Compatible</strong> – Well-supported with
libraries and documentation.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Multiple I/O Interfaces</strong> – SPI, I²C, UART, PWM, ADC,
and DAC.</p>
</blockquote></li>
<li><blockquote>
<p><strong>3.3V Logic Level</strong> – Compatible with your power
setup.</p>
</blockquote></li>
<li><blockquote>
<p><strong>External Antenna Support (UE Variant)</strong> – Allows for
better wireless range and signal strength.</p>
</blockquote></li>
</ul></th>
<th><ul>
<li><blockquote>
<p><strong>Older Bluetooth Version (4.2)</strong> – Lacks Bluetooth 5.0
features like longer range and lower power.</p>
</blockquote></li>
<li><blockquote>
<p><strong>Higher Power Consumption</strong> – Can drain batteries
faster than simpler microcontrollers.</p>
</blockquote></li>
<li><blockquote>
<p><strong>No Native USB-to-Serial Converter</strong> – Requires an
external chip or board for easier programming.</p>
</blockquote></li>
</ul></th>
</tr>
</thead>
<tbody>
</tbody>
</table>

I chose the ESP32-S3-WROOM-1-N4 over the ESP32-WROOM-32UE-N4 because it
has a more powerful dual-core processor, supports Bluetooth 5.0 for
better range and efficiency, and offers enhanced AI acceleration for
potential future applications. Additionally, it aligns well with
MicroPython support and the 3.3V power setup needed for the system.
