<img width="1654" height="2480" alt="Beige_and_Black_Colorful_Abstract_Modern_Art_Festival_Poster_with_bgc" src="https://github.com/user-attachments/assets/fd7cf30c-511f-414b-93d5-2c9c7feb6c71" />

<img width="1587" height="2245" alt="3 7v GND" src="https://github.com/user-attachments/assets/bca8c580-7300-4dc1-824f-e1efcfc72201" />
*this project is not in its final verison yet so all the models and code will be updated, once the materials are recived
wiring
Wiring

RTC + Screen (SCK/SCL → ESP32-C3 GPIO 9)
RTC + Screen (SDA → ESP32-C3 GPIO 8)

Other than that for the physical wiring (the former was for the code):

Battery → TP4056 input
Grounds are shared
3.7V is directly connected to the C3 3.3V

A button directly cuts the power from the charging board, the device does not have a deep sleep mode.

It should be noted that the components used were:

3.7V LiPo battery with preinstalled BMS
SH1106 1.4 inch OLED display
DS3231 RTC
Associated coin cell
Tactile button connected directly to the charger output positive terminal
TP4056 charger
M3 bolts and nuts

It should be noted that the code is not made by me completely, this was my first time working with a screen and wifi and rtc so it was too complex for me to reliably create, after some experimenantion with the codes seperatly like displaying hello world, connecting my esp32 to the wifi , connecting to the time server and some failures, i decided that i couldent completely create the code myself. This code is also not the final version, its only a test code for the prototype and proof of concept of the project.

However the case and cover, the wiring and fitting and the general selection of hardware aswell as the iterations and core of the poject was all done by me, along with a few parts of the code, the entirety of which i understand.

Explanation to the code

In my case the code will begin by starting the components.

Then it will check for a flag called firstboot.

If it is infact powering on for the first time then it will connect to the wifi
and then go to a server called (pool.ntp.org), sets to the current IST.

Then it inputs that into the RTC.

Updates the firstboot flag to false and saves it permanently and disables the wifi.

When it boots again it will read the false firstboot and skip the wifi part entirely.

This was made in Arduino IDE.

It also converts the 24 hour clock into 12 hour after gathering the data from the RTC,
calculates if its AM or PM,
and uses a text string to print the date.


| Name of components        | Amount  |  price($) | sources |
|---------------------------|---------|-----------|---------|
| E-paper 2.1 inch display  | 1       | 19.8      | [Amazon](https://www.amazon.in/gp/product/B07ZGQWKQR/ref=ox_sc_act_title_9?smid=A3OFE3UKIO43OW&psc=1)  |
| Tactile buttons           | 1(10)   | 1.05      | [Amazon](https://www.amazon.in/gp/product/B0DT18FM7J/ref=ox_sc_act_title_8?smid=A1UUD7CBBVVXIG&psc=1)  |
|  RTC (DS3231)             | 1       | 3.13      | [amazon](https://www.amazon.in/gp/product/B0BZL9TB1W/ref=ox_sc_act_title_3?smid=A1SYL30TCF83WC&psc=1)  |
|  SD card reader           | 1       | 1.04      | [Amazon](https://www.amazon.in/gp/product/B073Q2HY3Q/ref=ox_sc_act_title_4?smid=A2FGC2POOS3TS8&psc=1)  |
| SD card                   | 1       | 4.17      | [Amazon](https://www.amazon.in/gp/product/B0GVJRTL4D/ref=ox_sc_act_title_7?smid=AJ6SIZC8YQDZX&psc=1) |
| on/off switch             | 1(10)   | 0.57      | [Amazon](https://www.amazon.in/gp/product/B0B7NKGPYX/ref=ox_sc_act_title_1?smid=A366YFPXO3CTI5&psc=1)  |

Other than this youll also need filament, m3 bolts and nuts (8 of each), and some super glue

Motivation

This project was made because i despertaly needed a clock i could put on my desk, something i could wear on the go that was made by me, and something with a bit of gimick aswell
it built because i wanted to show that i could absoltly make something real and that my experince and skills werent theoretical

its unique because it uses commercial parts and simple assmbely that anyone could make
its super simple in its design and has a lot of functions for what its worth so you wont just find it useful as a watch but also something youll find yourself using day in and day out
