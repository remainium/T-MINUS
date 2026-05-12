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


* it should be noted that the code is not made by me, this was my first time working with a screen and wifi and rtc so it was too complex for me to reliably create, after some experimenantion with the codes seperatly like displaying hello world, connecting my esp3 to the wifi and some failures, i decided that i couldent completely create the code myself.

however the case and cover, the wiring and fitting and the general selection of hardware aswell as the iterations and core of the poject was all done by me.
