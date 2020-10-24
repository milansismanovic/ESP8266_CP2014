# ESP8266 with an 0.91 inch OLED CP2014
Trying out: https://www.aliexpress.com/item/33015504632.html

![alt text](https://ae01.alicdn.com/kf/HTB1xV4pV4naK1RjSZFBq6AW7VXah.jpg " 1 x 0.91 OLED ESP8266 Wifi Kit8 Development Board  ")

Looks like a great board with Wifi and OLED for below 10 USD.

However it requires some tuning to make it use in the Arduino IDE.

0.91s OLED connection are:
//SDA -- D4
//SCL -- D5
//RST -- D2 

## Installation
First you need to install the ESP8266 chip support in the Arduino IDE Board Manager as described here: 
https://github.com/esp8266/Arduino#installing-with-boards-manager


## Example 1 A little OLED Display demo
This demo shows the Adafruit library is working on this machine.

This code worked for me: https://github.com/adafruit/Adafruit_SSD1306/blob/master/examples/ssd1306_128x32_i2c/ssd1306_128x32_i2c.ino with only changing from:
#define OLED_RESET     4 // Reset pin # (or -1 if sharing Arduino reset pin)
to:
#define OLED_RESET     2 // Reset pin # (or -1 if sharing Arduino reset pin)

## Example 2 WIFI ESP8266 Demo
This example shows the Wifi is working on ths library: https://simplestuffmatters.com/wp-content/uploads/2017/10/ESP8266_LCD_Demo.ino

The OLED display didn't work for me though...

Changes required:
change from
```
#define OLED_SDA  2
#define OLED_SCL 14
#define OLED_RST  4
```
to
```
#define OLED_SDA  4
#define OLED_SCL 5
#define OLED_RST  2
```
and set your Wifi settings here:
```
//WIFI configuration
#define wifi_ssid "REPLACE WITH SSID"
#define wifi_password "REPLACE WITH PASSWORD"
```
