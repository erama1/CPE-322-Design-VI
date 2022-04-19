# Labs 1A-1D

## Lab 1A: Raspberry Pi Setup
### Raspberry Pi desktop preferences

* On Raspberry Pi desktop > Right click > Desktop Preferences > Appearance Settings
* Desktop (Layout, Picture, Color, Text Color, Documents, Wastebasket, Mounted Disks)
* Menu Bar (Size, Position, Color, Text Color)
* System (Font, Highlight Color, Highlight Text Color, Mouse Cursor)
* Defaults (For large, medium, or small screens)

### Find a [MAC address](https://en.wikipedia.org/wiki/MAC_address) of the [media access control](https://en.wikipedia.org/wiki/Medium_access_control) with an [oranizationally unique identifier](https://en.wikipedia.org/wiki/Organizationally_unique_identifier) (OUI), and an [IP address](https://en.wikipedia.org/wiki/IP_address) of the [Internet Protocol](https://en.wikipedia.org/wiki/Internet_Protocol)

* On Raspberry Pi OS, point (not click) the curser to the Wi-Fi icon at the right of the menu bar to see and write down the IP address such as 192.168.1.204 excluding the CIDR ([Classless Inter-Domain Routing](https://en.wikipedia.org/wiki/Classless_Inter-Domain_Routing)) notation of /24 suffix that indicates the number of bits of the prefix

https://user-images.githubusercontent.com/45573682/163911302-81871303-0511-43c6-bf5e-db05590d0278.mp4

## Lab 1B: Raspberry Pi Configuration
#### 1. Click the Raspberry Pi icon at the left of the menu bar to open applications menu > Preferences > Raspberry Pi Configuration > System
#### 2. Raspberry Pi Configuration > Display
#### 3. Raspberry Pi Configuration > Interfaces
#### 4. Raspberry Pi Configuration > Performance
#### 5. Raspberry Pi Configuration > Localization
#### 6. Click OK and click Yes for "Would you like to reboot now?"
https://user-images.githubusercontent.com/45573682/163913884-f72daaf0-b179-48eb-996f-a9c2470461d9.mp4



## Lab 1C: Startup Mailer
* Open up /home/pi/iot/lesson1/startup_mailer.py
```sh
$ nano startup_mailer.py
```
* Change RECIPIENT_EMAIL, GMAIL_USERNAME, and GOOGLE_APP_PASSWORD
* Replace HOSTNAME with the new Hostname in two instances
* Save the file by typing "control-x y enter"

![recipient](https://user-images.githubusercontent.com/45573682/163905796-b5f0990b-9909-41e9-9ad8-91a2d6795492.png)
![mailer](https://user-images.githubusercontent.com/45573682/163905685-182535c3-741c-46a7-885a-79fb4095133a.png)

### I was not receiving an email after reboot and needed to follow the below steps

If not receiving an email from the Raspberry Pi after reboot, create /lib/systemd/system/[startup.service](/lesson1/startup.service)
```sh
$ sudo nano /lib/systemd/system/startup.service
$ sudo systemctl daemon-reload
$ sudo systemctl enable startup.service
$ sudo reboot
```
![startup](https://user-images.githubusercontent.com/45573682/163905810-77161cd1-2548-4012-a48a-813c8493f493.png)

### Email from startup_mailer.py and after reboot
<img width="1302" alt="IP_email" src="https://user-images.githubusercontent.com/45573682/163912176-e0bc2547-de5c-45db-af02-a01d6c941210.png">


## Lab 1D: [SSH](https://en.wikipedia.org/wiki/Secure_Shell) and [VNC](https://en.wikipedia.org/wiki/Virtual_Network_Computing)

### Run an SSH client to log into Raspberry Pi
```sh
$ ssh pi@192.168.1.204
pi@raspberrypi:~ $ vncserver
```
<img width="745" alt="Screen Shot 2022-04-18 at 11 13 40 PM" src="https://user-images.githubusercontent.com/45573682/163913390-b51a0b18-2cca-467b-a493-150ffca8b5c8.png">

### Open VNC Viewer, and enter 192.168.1.204:1, username pi, and password
<img width="656" alt="Screen Shot 2022-04-18 at 11 16 11 PM" src="https://user-images.githubusercontent.com/45573682/163913441-e81e150c-43d3-4e06-8f59-26f2c3d9c468.png">
<img width="856" alt="Screen Shot 2022-04-18 at 11 16 55 PM" src="https://user-images.githubusercontent.com/45573682/163913455-22012c96-f6db-4db1-9312-248ac9b5af6f.png">



