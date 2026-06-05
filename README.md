<img width="1587" height="2245" alt="Beige and Black Colorful Abstract Modern Art Festival Poster" src="https://github.com/user-attachments/assets/65ca9d6a-2658-4900-94d7-d23c882fe758" />
<img width="2000" height="2000" alt="T-MINUS github repo (1)" src="https://github.com/user-attachments/assets/b3aaec4a-f5e3-4be0-9102-a017f68cfa43" />
<img width="2000" height="2000" alt="T-MINUS github repo" src="https://github.com/user-attachments/assets/99e0fa00-e1e8-4c7e-a5c6-d1a5af18216c" />
<img width="1600" height="900" alt="WhatsApp Image 2026-05-18 at 2 11 47 AM" src="https://github.com/user-attachments/assets/9365c7d5-03b3-44f6-8ffd-d181459a79ee" />
<img width="1600" height="900" alt="WhatsApp Image 2026-05-18 at 2 11 46 AM" src="https://github.com/user-attachments/assets/6e6999e6-30cd-49ea-81e6-1743a6bf4d64" />
<img width="1600" height="900" alt="WhatsApp Image 2026-05-16 at 7 18 47 PM" src="https://github.com/user-attachments/assets/3683ac4a-5d77-432e-9f3c-ba2da6a7c041" />
<img width="4608" height="3456" alt="DSCN4701 1" src="https://github.com/user-attachments/assets/ca0e07b7-cfd8-44fd-b53d-77fa00c88992" />
<img width="4608" height="3456" alt="DSCN4702 1" src="https://github.com/user-attachments/assets/4223b547-5c93-4102-862f-fc956f1162f1" />
<img width="4608" height="3456" alt="DSCN4703 1" src="https://github.com/user-attachments/assets/38acc22f-3e06-4714-b793-2b23a11f1c13" />
<img width="1600" height="900" alt="WhatsApp Image 2026-05-10 at 5 32 46 PM (2)" src="https://github.com/user-attachments/assets/935b9678-673b-417c-9b79-c124db26697b" />
<img width="1600" height="900" alt="WhatsApp Image 2026-05-10 at 5 32 46 PM (1)" src="https://github.com/user-attachments/assets/efd4f4d8-d076-4e6c-9527-f37bab7787f9" />
<img width="900" height="1600" alt="WhatsApp Image 2026-05-10 at 5 32 46 PM" src="https://github.com/user-attachments/assets/1d39a90c-89e0-4796-807c-69a13de55f97" />
wiring
rtc, screen sck/scl - esp 32 c3 GPIO 9
rtc, screen sda     - esp 32 c3 GPIO 8

other than that for the physical wiring (the former was for the code)

battery to tp4056 input
grounds are shared
3.7v is directly connected to the c3 3.3v

a button directly cuts the power from the charging board, the device does not have a deep sleep mode.

it should be noted that the componets used were
3.7v lipo battery with preinstalled BMS
SH1106 1.4 inch OLED display
DS3231 RTC
a associated coin cell
a tactile button connected directly to the charger output positive terminal
the TP4056 charger
M3 bolts and nuts 


* it should be noted that the code is not made by me completely, this was my first time working with a screen and wifi and rtc so it was too complex for me to reliably create, after some experimenantion with the codes seperatly like displaying hello world, connecting my esp32 to the wifi , connecting to the time server and some failures, i decided that i couldent completely create the code myself. This code is also not the final version, its only a test code for the prototype and proof of concept of the project.

however the case and cover, the wiring and fitting and the general selection of hardware aswell as the iterations and core of the poject was all done by me, along with a few parts of the code, the entirety of which i understand.



an explanation to the code

in my case the code will begin by starting the components

then it will check for a flag called firstboot

if it is infact powering on for the first time then it will connect to the wifi
and then go to a server called (pool.ntp.org) , sets to the current ist

then it inputs that into the RTC

updates the firstboot flag to false and saves it permanently and disables the wifi

when it boots agian it will read the false firstbott and skip the wifi part entirly

this was made in arduino ide.

it also converts the 24 hour clock into 12 hour after gathering the data from the rtc
calculates if its AM or PM 

and uses a text string to print the date

| Name of components        | Amount  |  price($) | sources |
|---------------------------|---------|-----------|---------|
| E-paper 2.1 inch display  | 1       | 19.8      | [Amazon](https://www.amazon.in/gp/product/B07ZGQWKQR/ref=ox_sc_act_title_9?smid=A3OFE3UKIO43OW&psc=1)  |
| Tactile buttons           | 1(10)   | 1.05      | [Amazon](https://www.amazon.in/gp/product/B0DT18FM7J/ref=ox_sc_act_title_8?smid=A1UUD7CBBVVXIG&psc=1)  |
|  RTC (DS3231)             | 1       | 3.13      | [amazon](https://www.amazon.in/gp/product/B0BZL9TB1W/ref=ox_sc_act_title_3?smid=A1SYL30TCF83WC&psc=1)  |
|  SD card reader           | 1       | 1.04      | [Amazon](https://www.amazon.in/gp/product/B073Q2HY3Q/ref=ox_sc_act_title_4?smid=A2FGC2POOS3TS8&psc=1)  |
| SD card                   | 1       | 4.17      | [Amazon](https://www.amazon.in/gp/product/B0GVJRTL4D/ref=ox_sc_act_title_7?smid=AJ6SIZC8YQDZX&psc=1) |
| on/off switch             | 1(10)   | 0.57      | [Amazon](https://www.amazon.in/gp/product/B0B7NKGPYX/ref=ox_sc_act_title_1?smid=A366YFPXO3CTI5&psc=1)  |
