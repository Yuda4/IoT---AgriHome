# IoT course, Ariel university
**_AgriHome_** - A smart plant system that measure air temperature and humidity, soil moisture and using lamp for warnings when high sampling indices.<br />
AgriHome is using:<br />
  * ESP32 - System On Chip Microcontoller including WiFi and Bluetooth.<br />
  * BreadBoard and jumper cables.<br />
  * DHT11 - Temperature and Humidity sensor.<br />
  * Soil Moisture Sensor. <br />
  * Lamp - Color led. <br />

<img src ="https://user-images.githubusercontent.com/33513480/64234737-95fed900-ceff-11e9-9c39-b770713b23a7.jpg" width="100">
<img src = "https://user-images.githubusercontent.com/33513480/64234507-2f79bb00-ceff-11e9-98bb-39fb8db90de5.jpg" width="100">
<img src = "https://user-images.githubusercontent.com/33513480/64234785-aca53000-ceff-11e9-955e-e9767c19209b.jpg" width="100">



## Liberaries using ESP32
 * WiFi.h - This library allows ESP32 to connect your router.<br />
 * PubSubClient.h - This library allows you to send and receive MQTT messages.<br />
 * DHT.h - This library allows DHT11, DHT21 and DHT22 sensors for measuring temperature and humidity.<br />
 * SSD1306Wire - This library allows OLED display

## General view
The ESP device models through sensors several parameters - air and soil temperature and humidity. It transmits the screen, through appropriate Service Edge - (Local services) Red-Node, to the cloud. The communication between ESP device and the cloud will be done via WiFi.<br />
The data will be stored long-term in Firebase database, and will be displayed in graphs: each parameter (temperature, humidity and soil moisture) has a graph that allows viewing historical data based on date / time segmentation.<br />
The data will be analyzed through BigML website and produced a model that allows forecasting and decision-making, for example on the basis of a decision tree, and the model structure can be viewed in a suitable graph.
