# Home Assistant Config

My Home Assistant stack operates on an Ubuntu 18.04.2 LTS host using docker containers.

## Hardware
Name|Use
----|---
Intel NUC KIT NUC6i3SYK, 8 GB RAM, 500GB SSD|Server PC
CC2531 USB Sniffer|Zigbee communication
Nortek HUSBZB-1 USB Stick|Z-Wave communication

## Devices
Name|Protocol/Connection|Class(es)
----|-------------------|---------
GE Link smart LED light bulb, BR30 soft white (2700K)|Zigbee|Light
Philips Hue dimmer switch|Zigbee|Remote
Centralite White Swiss power outlet switch with power meter|Zigbee|Switch, Energy
Samsung SmartThings Multipurpose Sensor|Zigbee|Door, Temperature
Monoprice Z-Wave Plus Door and Window Sensor|Z-Wave Plus|Door
GoControl Z-Wave Dimmable LED Light Bulb, LB60Z-1|Z-Wave Plus|Light
GE Z-Wave Wireless Smart Lighting Control Appliance Module 12719|Z-Wave|Light
Kasa Smart WiFi Plug by TP-Link HS100|Wi-Fi|Switch
Logitech Harmony Hub|Wi-Fi|Remote, Media Player
Apple TV 4K|Gigabit Ethernet|Media Player
Nvidia Shield|Gigabit Ethernet|Media Player
Apple iPhone X|Wi-Fi, Cellular, GPS|Device Tracker
WyzeCam v2|Wi-Fi|Camera, Motion
UniFi Video Camera G3|Ethernet|Camera, Motion

## Software Containers
Name|Image|Notes
----|-----|-----
[Home Assistant](https://www.home-assistant.io/)|[homeassistant/home-assistant](https://hub.docker.com/r/homeassistant/home-assistant/)|Home Assistant
[Zigbee2mqtt](https://www.zigbee2mqtt.io/)|[koenkk/zigbee2mqtt](https://hub.docker.com/r/koenkk/zigbee2mqtt/)|Listens for zigbee network communication and sends it to the MQTT message broker
[Caddy](https://caddyserver.com/)|[adriel/caddy](https://hub.docker.com/r/adriel/caddy)|Reverse proxy, automatic https
[Eclipse Mosquitto](https://mosquitto.org/)|[eclipse-mosquitto](https://hub.docker.com/_/eclipse-mosquitto)|Message broker
[Homebridge](https://homebridge.io/)|[oznu/homebridge](https://hub.docker.com/r/oznu/homebridge)|Used to expose cameras from MotionEye to Apple Homekit
[Node-RED](https://nodered.org/)|[nodered/node-red-docker:v8](https://hub.docker.com/r/nodered/node-red-docker)|Takes care of automating remote button presses, alexa commands, notifications, lighting automations
[MariaDB](https://mariadb.org/)|[mariadb](https://hub.docker.com/_/mariadb)|Home Assistant recorder database
[MotionEye](https://github.com/ccrisan/motioneye)|[ccrisan/motioneye](https://hub.docker.com/r/ccrisan/motioneye)|Handles MQTT communication when motion detected from cameras