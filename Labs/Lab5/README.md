# Lab 5 - Paho-MQTT

## Study the GitHUb [repository](https://github.com/kevinwlu/iot) Lesson 5 labs

## Install Paho-MQTT &  Run subcpu.py and pubcpu.py
### On Raspberry Pi, install and run Mosquitto to subscribe on one terminal and publish on another
```sh
$ sudo apt update
$ sudo apt install mosquitto mosquitto-clients
$ mosquitto_sub -h localhost -v -t "\$SYS/#"
```
* Press control-c to stop mosquitto_sub
```sh
$ service mosquitto status
$ netstat -tln
```
* [mqtt.eclipseprojects.io](https://mqtt.eclipseprojects.io/) is a public test MQTT broker service. It currently listens on the following ports:
  * 1883 : MQTT over unencrypted TCP
  * 8883 : MQTT over encrypted TCP
  * 80 : MQTT over unencrypted WebSockets (note: URL must be /mqtt )
  * 443 : MQTT over encrypted WebSockets (note: URL must be /mqtt )
* [Internet Assigned Numbers Authority](https://en.wikipedia.org/wiki/Internet_Assigned_Numbers_Authority) (IANA) [Service Name and Transport Protocol Port Number Registry](https://www.iana.org/assignments/service-names-port-numbers/service-names-port-numbers.xhtml)
  * 3306 : MySQL
  * 22 : SSH
  * 5900/5901/6001 : VNC
#### Terminal 1
```sh
$ mosquitto_sub -h localhost -v -t test/topic &
```
#### Terminal 2
```sh
$ mosquitto_pub -h localhost -t test/topic -m "Hello"
```
### Intall Paho and run code to subscribe on one terminal and publish on another
```sh
$ sudo pip3 install -U paho-mqtt
$ git clone https://github.com/eclipse/paho.mqtt.python.git
$ cd ~/iot/lesson5
$ python3 client.py
```
#### Terminal 1 (press control-c to stop)
```sh
$ python3 sub.py
```
#### Terminal 2
```sh
$ python3 pub.py
```
#### Terminal 1 (press control-c to stop)
```sh
$ python3 sub-multiple.py
```
#### Terminal 2
```sh
$ python3 pub-multiple.py
```
#### Terminal 1 (press control-c to stop)
```sh
$ python3 subcpu.py
```
#### Terminal 2
```sh
$ python3 pubcpu.py
```
