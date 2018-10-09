# WiFi Connector

This library provides support for connecting to WiFi on single channel ESP8266 devices.

When called it will attempt to read an SSID, password and hostname from EEPROM and make a connection. If it finds those values to be missing, or for any reason cannot connect with them, it will open an access point.

The access point will present itself as the MAC address of the device and a browser can be pointed to 192.168.4.1 to configure new credentials. These will then be stored in the EEPROM and can be used again once the device has been restarted.

Clone or submodule the library into the lib folder of your project. You can use the library as a submodule with the command:

git submodule add https://github.com/barnsleyskunkworks/wifi-connector WiFiConnector
git commit -m "Added WiFiConnector submodule"

Examples usage:

'''c
#include <WiFiConnector.h>

WiFiConnector wifiConnector;

wifiConnector.connectWiFi();
if (wifiConnector.isConnected()) {
  wifiConnector.handleClient();
}
'''