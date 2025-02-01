# Task-5
Iot based "Air quality monitoring system in food industry"
The Air Quality Monitoring System using the VSD Squadron Mini (CH32V003) RISC-V microcontroller board is designed to ensure safe and optimal environmental conditions in food production and storage facilities. It leverages various sensors to monitor gas levels, temperature, and humidity, providing real-time data and automated control for safety and quality management in the food industry. This system integrates a gas sensor (MQ-135) to detect harmful gases such as CO2, ammonia, and smoke, a temperature and humidity sensor (DHT11/DHT22) for environmental monitoring, and a Wi-Fi module (ESP8266/ESP32) for cloud connectivity. The system can trigger external devices like ventilation systems or alarms using a relay module, ensuring that unsafe conditions are addressed promptly. By uploading sensor data to a cloud platform like ThingSpeak, this solution offers real-time monitoring, data visualization, and remote alerts, making it an effective tool for maintaining safe working and storage environments in food-related industries.

Key Features:
Real-Time Environmental Monitoring:

The system continuously monitors air quality, temperature, and humidity levels, ensuring that conditions within food production or storage areas remain optimal. The MQ-135 gas sensor detects harmful gases, while the DHT11/DHT22 sensors provide accurate data on temperature and humidity.
Cloud Integration for Remote Monitoring:

By using an ESP8266/ESP32 Wi-Fi module, the system uploads sensor data to a cloud platform like ThingSpeak, enabling real-time monitoring and data visualization from any internet-enabled device. This allows facility managers to keep track of environmental conditions remotely.
Automated Control for Safety:

The system can trigger actions such as activating ventilation systems or sounding alarms using the relay module when hazardous gas levels or unsafe temperature/humidity readings are detected, ensuring immediate corrective actions without manual intervention.
Cost-Effective RISC-V Architecture:

The VSD Squadron Mini (CH32V003) microcontroller is based on RISC-V architecture, which offers a low-cost, power-efficient, and high-performance solution for embedded systems. It handles sensor data processing, communication, and control tasks effectively.
Scalability:

The system is easily scalable, allowing additional sensors or control modules to be added as needed. This makes it suitable for small-scale or large-scale food production facilities.
Data Logging and Trend Analysis:

The cloud platform stores data over time, enabling trend analysis and helping identify potential issues before they become critical, which supports long-term decision-making for facility management.
component list for the Air Quality Monitoring System using the VSD Squadron Mini (CH32V003) RISC-V board:

1. VSD Squadron Mini (CH32V003) Development Board
Description: The main microcontroller for controlling the system and processing the sensor data.
Quantity: 1
Specification:
RISC-V architecture
32-bit processor
64KB Flash, 8KB SRAM
32 GPIO pins, ADC channels, UART, SPI, I2C interfaces
2. MQ-135 Gas Sensor
Description: This sensor detects gases such as CO2, Ammonia, Smoke, and VOC (Volatile Organic Compounds).
Quantity: 1
Specification:
Power Supply: 3.3V/5V
Output: Analog (AOUT), Digital (DO)
Operating temperature: 0-50°C
3. DHT11/DHT22 Temperature and Humidity Sensor
Description: Measures temperature and humidity in the air.
Quantity: 1
Specification:
Power Supply: 3.3V/5V
Digital Output
DHT11: 20-90% humidity, 0-50°C temperature range
DHT22: 0-100% humidity, -40°C to 80°C temperature range
  
4. ESP8266/ESP32 Wi-Fi Module
Description: Provides Wi-Fi connectivity to upload sensor data to the cloud platform (e.g., ThingSpeak).
Quantity: 1
Specification:
Power Supply: 3.3V (ESP32)
Communication: UART (TX/RX)
Wi-Fi: 802.11 b/g/n
Can be used to send sensor data to the cloud.
  
5. Relay Module (Optional)
Description: This module is used to control external devices like ventilation fans or alarms when unsafe conditions are detected.
Quantity: 1
Specification:
Power Supply: 5V
Output: Control up to 10A at 250V AC or 30V DC
Relay module with Optocoupler for isolation
Input: Low-voltage signal (3.3V/5V)
  
6. Jumper Wires
Description: Used for connecting the components to the microcontroller board.
Quantity: 1 set
Specification:
Male to Male jumper wires for breadboard connections
  
7. Breadboard
Description: For easy prototyping of the system without soldering.
Quantity: 1
Specification:
Standard size for connecting components
  
8. 3.3V/5V Power Supply
Description: Provides power to the VSD Squadron Mini board and other components.
Quantity: 1
Specification:
Power Supply Voltage: 5V or 3.3V (depending on components)
Can use a USB power supply or a DC power adapter
  
9. Capacitors and Resistors (Optional)
Description: You might need some small-value capacitors (e.g., 10uF) for debouncing or filtering noise in the signals from the sensors.
Quantity: 1 set
Specification:
Resistors: 10kΩ for pull-up on DHT11/DHT22
Capacitors: 10uF for stabilizing the power supply 
  
10. Micro USB Cable (for VSD Squadron Mini)
Description: Used to connect the VSD Squadron Mini to a computer for programming and power.
Quantity: 1
Specification:
Type: Micro USB
Pin Connections.
VSD Squadron Mini (CH32V003) Pin Connections:
The VSD Squadron Mini (CH32V003) has various GPIO pins and ADC channels for interfacing with sensors and other modules. Below are the connections for each component.

1. MQ-135 Gas Sensor
The MQ-135 sensor has both an analog output (AOUT) and a digital output (DO). For this project, we'll use the analog output (AOUT) to detect gas concentrations.

VCC: Connect to 3.3V on the VSD Squadron Mini (CH32V003).
GND: Connect to GND on the VSD Squadron Mini.
Analog Output (AOUT): Connect to ADC pin (GPIO5) on the VSD Squadron Mini (or any available ADC pin for reading analog values).
Digital Output (DO): Optional (you can leave this unconnected unless you want a digital threshold output, typically not used for this project).
2. DHT11/DHT22 Temperature and Humidity Sensor
The DHT11 or DHT22 sensor uses a single-wire communication protocol. You'll connect its data pin to a GPIO pin on the CH32V003.

VCC: Connect to 3.3V (or 5V, depending on the sensor model) on the VSD Squadron Mini.
GND: Connect to GND on the VSD Squadron Mini.
Data Pin: Connect to GPIO6 on the VSD Squadron Mini (or any available GPIO pin). You may need a 10kΩ pull-up resistor between the Data Pin and VCC to stabilize the signal.
3. ESP8266/ESP32 Wi-Fi Module
The ESP8266 or ESP32 Wi-Fi module provides the system with internet connectivity to upload sensor data to a cloud platform.

VCC: Connect to 3.3V (or 5V, depending on the module) on the VSD Squadron Mini.
GND: Connect to GND on the VSD Squadron Mini.
TX Pin (ESP8266/ESP32): Connect to the RX Pin (GPIO1) on the VSD Squadron Mini.
RX Pin (ESP8266/ESP32): Connect to the TX Pin (GPIO0) on the VSD Squadron Mini.
4. Relay Module
The Relay Module can be used to control external devices like ventilation fans or alarms based on sensor readings.

VCC: Connect to 5V (or 3.3V, depending on the relay) on the VSD Squadron Mini.
GND: Connect to GND on the VSD Squadron Mini.
Control Pin: Connect to GPIO7
Pin Connections Table:
Component	VSD Squadron Mini (CH32V003) Pin	Connection
MQ-135 Gas Sensor	VCC (3.3V)	3.3V on CH32V003
GND	GND on CH32V003
AOUT (Analog Output)	GPIO5 (ADC Pin on CH32V003)
DHT11/DHT22 Sensor	VCC	3.3V (or 5V based on sensor)
GND	GND on CH32V003
Data Pin	GPIO6 (Digital Pin on CH32V003)
ESP8266/ESP32 Wi-Fi Module	VCC	3.3V (or 5V) on CH32V003
GND	GND on CH32V003
TX Pin	GPIO1 (RX on CH32V003)
RX Pin	GPIO0 (TX on CH32V003)
Relay Module	VCC	5V (or 3.3V depending on relay)
GND	GND on CH32V003
Control Pin	GPIO7 The Air Quality Monitoring System using the VSD Squadron Mini (CH32V003) RISC-V microcontroller works by continuously monitoring the air quality, temperature, and humidity in a facility (such as a food production or storage area) and taking necessary actions based on the sensor readings. Here's a step-by-step breakdown of how the system works:

1. Data Collection:
Gas Detection (MQ-135 Gas Sensor):

The MQ-135 gas sensor detects harmful gases such as CO2, ammonia, smoke, and other volatile organic compounds (VOC). The sensor has both an analog output (AOUT) and a digital output (DO). The analog output is connected to the ADC pin of the VSD Squadron Mini (CH32V003) to measure the concentration of gases.
The microcontroller continuously reads the analog voltage from the MQ-135 sensor, which is proportional to the gas concentration in the environment.
Temperature and Humidity (DHT11/DHT22 Sensor):

The DHT11 or DHT22 sensor measures the temperature and humidity of the surrounding air. The data is collected via the data pin connected to the GPIO pin of the CH32V003.
The sensor sends digital signals containing temperature and humidity data, which the microcontroller processes.
2. Data Processing and Threshold Checking:
The VSD Squadron Mini (CH32V003) processes the data from the MQ-135 gas sensor and the DHT11/DHT22 sensor.
It compares the collected data against predefined thresholds:
If the gas concentration exceeds a safe threshold (for example, when the CO2 level is too high), the system detects this condition as unsafe.
Similarly, if the temperature or humidity values fall outside acceptable ranges (e.g., the temperature gets too high or humidity gets too low for proper food storage), the system identifies this as an issue.
3. Automated Actions:
Triggering the Relay (External Device Control):
If the system detects unsafe conditions (such as high gas concentration or dangerous temperature/humidity), it activates a relay connected to a device (e.g., ventilation fans or alarms).
The VSD Squadron Mini (CH32V003) microcontroller sends a signal to the relay through one of its GPIO pins, turning on/off the connected devices to correct the environment:
If high gas concentrations are detected, the system can activate ventilation to bring in fresh air.
If the temperature or humidity exceeds safe levels, the system can trigger cooling or humidification systems.
4. Data Upload to Cloud:
The ESP8266/ESP32 Wi-Fi module connects the system to the internet. The VSD Squadron Mini (CH32V003) sends sensor data via UART to the ESP8266/ESP32, which uploads the data to a cloud platform such as ThingSpeak.
In the cloud platform, the data is visualized in real-time as graphs and charts. Facility managers or operators can monitor the air quality, temperature, and humidity from anywhere using a web browser or mobile device.
5. Remote Monitoring and Alerts:
Real-Time Monitoring:
On the cloud platform, users can view live data for gas concentration, temperature, and humidity levels, allowing them to monitor the facility's environmental conditions from anywhere in the world.
Alerting:
The cloud platform can be configured to send email or SMS alerts when environmental conditions go outside predefined safe limits. For example, if the gas levels become too high or the temperature goes out of range, the system will send an alert to the responsible person.
6. Long-Term Data Logging and Analysis:
Data Logging:

The system stores sensor data over time on the cloud platform. This historical data can be used for trend analysis and to identify patterns in environmental conditions.
For example, over time, the system may reveal that certain areas of the facility tend to have higher CO2 levels or that the temperature fluctuates during specific times of day. This allows for predictive maintenance and better facility management.
Analysis and Optimization:

By analyzing historical data, food production facilities can adjust environmental controls, improve safety, and optimize energy usage (e.g., adjusting heating, ventilation, and air conditioning (HVAC) systems based on patterns).
System Workflow (Summary):
Sensors Collect Data: The MQ-135 sensor monitors gas concentrations, and the DHT11/DHT22 sensor monitors temperature and humidity.
Data Processing: The VSD Squadron Mini (CH32V003) processes this data and compares it to predefined safe thresholds.
Automated Actions: If unsafe conditions are detected, the system triggers actions like activating ventilation or sounding an alarm via the relay module.
Data Upload to Cloud: The ESP8266/ESP32 Wi-Fi module uploads the sensor data to a cloud platform like ThingSpeak.
Remote Monitoring & Alerts: Facility managers can monitor the data remotely and receive alerts when conditions go outside safe thresholds.
Long-Term Logging & Analysis: The system logs historical data for trend analysis, enabling long-term decision-making for safety and efficiency.
Key Features of the Air Quality Monitoring System:
Real-Time Environmental Monitoring:

Continuously monitors gas concentrations, temperature, and humidity to ensure that the environment remains safe and suitable for food production and storage.
Cloud Integration for Remote Monitoring:

Uses the ESP8266/ESP32 Wi-Fi module to upload data to a cloud platform (e.g., ThingSpeak), allowing for real-time monitoring of environmental conditions from any internet-connected device.
Automated Actions for Safety:

Automatically activates devices like ventilation fans or alarms using a relay module when unsafe environmental conditions (e.g., high gas concentration, temperature, or humidity) are detected.
Data Logging and Trend Analysis:

Stores sensor data in the cloud for historical analysis and long-term trend monitoring, enabling users to track environmental changes over time and take proactive measures.
User Alerts:

Configurable alerts that can be sent via email or SMS when critical thresholds for temperature, humidity, or gas concentration are crossed, ensuring prompt intervention.
Low-Cost and Efficient RISC-V Architecture:

The VSD Squadron Mini (CH32V003) microcontroller, based on RISC-V architecture, offers a cost-effective and power-efficient solution for embedded systems, making it ideal for continuous operation in industrial environments.
Scalability:

The system is easily scalable to monitor larger facilities or additional areas by simply adding more sensors or expanding the cloud-based data dashboard.
Simple Sensor Integration:

Integrates easily with commonly used sensors like MQ-135 for gas detection and DHT11/DHT22 for temperature and humidity, offering versatility for various monitoring needs.
Possible Extensions and Enhancements:
Integration with More Sensors:

VOC (Volatile Organic Compound) Sensors: Add VOC sensors like MQ-7 or CCS811 to monitor a wider range of gases, especially in food processing environments where chemical vapors may be a concern.
CO and CO2 Sensors: Enhance the system with specific sensors for detecting carbon monoxide (CO) and carbon dioxide (CO2) to ensure the air is safe for workers in confined spaces or areas where gases are a concern.
PM2.5 Particulate Matter Sensor: Incorporate PM2.5 sensors to monitor air quality in terms of particulate matter (e.g., dust and soot), especially for environments where cleanliness is crucial, like food processing areas.
Machine Learning for Predictive Analysis:

Implement machine learning (ML) algorithms to analyze sensor data and predict future environmental changes. For example, the system could predict gas levels or temperature changes based on historical data, allowing for early intervention before issues arise.
Use machine learning models to detect anomalies in sensor data and alert the system when irregular patterns are identified, improving accuracy and preventing false alarms.
Mobile App Integration:

Develop a mobile app that connects to the cloud platform, allowing managers or operators to receive notifications, view live data, and control the system remotely from smartphones or tablets.
The app could include push notifications for alerts and an interactive dashboard with graphs to visualize real-time data.
Advanced Control of External Devices:

Integrate with smart HVAC systems for automated temperature and humidity regulation based on real-time sensor data.
Add the capability to control automated blinds or smart fans to optimize airflow and regulate the indoor environment in response to sensor data.
Implement fan speed control or heating/cooling regulation based on the sensor inputs for more granular control over the environment.
Integration with IoT-based Safety Systems:

Link the system with other IoT-based safety equipment, such as fire alarms, sprinkler systems, or gas leak detectors, for a more comprehensive industrial safety solution.
Enable the system to trigger safety protocols in the event of multiple simultaneous hazards, for example, combining high gas levels with high temperatures to trigger automatic emergency response systems.
Energy Optimization:

Integrate the system with energy management systems to optimize the use of heating, cooling, and ventilation equipment based on real-time environmental data. This could reduce energy consumption and operating costs.
Use the system to track and optimize the energy usage of ventilation systems or cooling units, improving overall efficiency and sustainability.
Multi-Facility Support:

Extend the system to support multiple facilities or production lines by aggregating sensor data from various locations. This could be particularly useful for managing large industrial plants or distribution centers with multiple warehouses.
Implement a centralized dashboard that can monitor and control different locations in real-time, allowing managers to oversee several sites from a single interface.
Integration with Environmental Compliance Systems:

Link the system with industry-specific regulatory compliance tools to automatically generate reports that ensure air quality standards are met in the food industry or other sectors.
The system could generate detailed compliance reports on air quality, temperature, and humidity, making it easier for companies to adhere to environmental and safety regulations.
Battery-Operated, Low-Power Mode:

For remote or off-grid installations, integrate a battery-powered solution with low-power sensors and a low-power mode for the microcontroller, enabling the system to run for extended periods without constant power supply.
Use solar panels or other renewable energy sources to power the system in environmentally-conscious or remote locations.



CONCLUSION 
The **Air Quality Monitoring System** using the **VSD Squadron Mini (CH32V003)** RISC-V microcontroller provides an effective and efficient solution for ensuring safe environmental conditions in food production and storage facilities. By continuously monitoring gas concentrations, temperature, and humidity through sensors like the **MQ-135** and **DHT11/DHT22**, the system provides real-time data and automates corrective actions such as activating ventilation systems or triggering alarms. Cloud integration via the **ESP8266/ESP32** enables remote monitoring and alerts, enhancing operational efficiency. The system's low-cost, scalable, and reliable design ensures ease of implementation, making it suitable for small to large-scale applications. With potential extensions like machine learning, mobile app integration, and energy optimization, the system offers significant opportunities for future enhancement. Ultimately, this project improves food safety, air quality, and operational control, ensuring a safer and more efficient working environment for both products and personnel.
