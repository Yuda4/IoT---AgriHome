# IoT course, Ariel university
**_AgriHome_** - A smart plant system that measure air temperature and humidity, soil moisture and using lamp for warnings when high sampling indices.<br />
AgriHome is using:<br />
  * ESP32 - System On Chip Microcontoller including WiFi and Bluetooth.<br />
  <img src ="https://user-images.githubusercontent.com/33513480/64234737-95fed900-ceff-11e9-9c39-b770713b23a7.jpg" width="150">
  * BreadBoard and jumper cables.<br />
  <img src ="https://user-images.githubusercontent.com/33513480/64235132-63091500-cf00-11e9-9c2d-77ae6247b0c6.jpg" width="150">
  * DHT11 - Temperature and Humidity sensor.<br />
  <img src = "https://user-images.githubusercontent.com/33513480/64234507-2f79bb00-ceff-11e9-98bb-39fb8db90de5.jpg" width="150">
  * Soil Moisture Sensor.<br />
  <img src = "https://user-images.githubusercontent.com/33513480/64234785-aca53000-ceff-11e9-955e-e9767c19209b.jpg" width="150">
  * Lamp - Color led. <br />
  <img src = "https://user-images.githubusercontent.com/33513480/64235517-31dd1480-cf01-11e9-95b4-f3dfd4887cea.jpg" width="150">

## Liberaries using ESP32
 * WiFi.h - This library allows ESP32 to connect your router.<br />
 * PubSubClient.h - This library allows you to send and receive MQTT messages.<br />
 * DHT.h - This library allows DHT11, DHT21 and DHT22 sensors for measuring temperature and humidity.<br />
 * SSD1306Wire - This library allows OLED display

## General view
The ESP device models through sensors several parameters - air and soil temperature and humidity. It transmits the screen, through appropriate Service Edge - (Local services) Red-Node, to the cloud. The communication between ESP device and the cloud will be done via WiFi.<br />
The data will be stored long-term in Firebase database, and will be displayed in graphs: each parameter (temperature, humidity and soil moisture) has a graph that allows viewing historical data based on date / time segmentation.<br />
The data will be analyzed through BigML website and produced a model that allows forecasting and decision-making, for example on the basis of a decision tree, and the model structure can be viewed in a suitable graph.

## Node-Red flows
### First flow - getting data from sensors to Node-red, using Mqtt protocol. </br>
All sensors are connected to a function that:
 * Combine data to a Json file to store it in Firebase database.
 * Combine data to a Csv file to store it in a local folder in computer.

<img src ="Node-red/Flow%20GetDataFromTheSensors.png" width="800">
</br>


