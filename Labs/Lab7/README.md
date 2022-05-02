# Lab 7 - ThingSpeak and Google Sheets

## Study the GitHub [repository]() Lesson 7
## Sign up and log in MathWorks ThingSpeak
* Sign up and log in [ThingSpeak](https://thingspeak.com)
* Create new channel cpu_loop with field1 cpu_pc and field2 mem_avail_mb
* Copy the Write API Key from [channels](https://thingspeak.com/channels)
* [ThingSpeak licensing FAQ](https://thingspeak.com/pages/license_faq) (frequently asked questions)

## Run thingspeak_cpu_loop.py or thinkspeak_feed.py in a demo folder
```sh
$ sudo pip3 install -U psutil
$ cd ~/demo
$ cp ~/iot/lesson7/thingspeak_cpu_loop.py .
$ cp ~/iot/lesson7/thingspeak_feed.py .
$ cat thingspeak_cpu_loop.py
$ cat thingspeak_feed.py
$ python3 thingspeak_feed.py
An API key savefile was not found. Enter Write API Key >>>
Should we save this key for future use? [y/N] >>>
```
![thingspeak](https://user-images.githubusercontent.com/45573682/166174870-010850c0-f689-4d82-b519-2a1b24459f6f.png)

* If yes, the Write API Key is saved in API_KEY.pickle
* Alternatively, replace YOURKEYHERE with the Write API in Line 10 of thingspeak_cpu_loop.py

## Install gspread and oauth2client
```sh
$ sudo pip3 install -U gspread oauth2client
```
## Log in the Google Cloud Platform Identity and Access Management, create a project cpudata, enable both Drive API and Sheets API, create and download service account JSON key file
* Click "Create" and enter the project name, e.g., cpudata
* &equiv; > APIs & Services > + Enable APIs & Services > Enable both Drive API and Sheets API
* Credential > Create Credentials > Create service account key > Service account > cpudata > JSON key type > Create > download cpudata-xxxxxxxxxxxx.json

## Copy system_info.py and rpi_spreadsheet.py to ~/demo
* On Raspberry Pi OS (Bullseye), change /opt/vc/bin/vcgencmd to /usr/bin/vcgencmd in system_info.py
```sh
$ cd demo
$ cp ~/iot/lesson3/system_info.py .
$ cp ~/iot/lesson7/rpi_spreadsheet.py .
```
### If the JSON key file (* = xxxxxxxxxxxx) is on a different computer, secure copy it to the same directory as cpu_spreadsheet.py
```sh
$ scp cpudata-*.json pi@192.168.x.xxx:/home/pi/demo
```
### If the the JSON key file is on a Raspberry Pi, move it to the same directory as cpu_spreadsheet.py
```sh
$ mv ~/Downloads/cpudata-*.json ~/demo
```

## Start a new Google sheet cpudata, share it with the client email in the JSON file, delete Rows 2 to 1000, and edit the header cells
* Go to [Google Sheets](https://docs.google.com/spreadsheets/u/0)
* Start a new spreadsheet and name it cpudata
* Share the spreadsheet with the "client_email" address in the .json file, select “Share,” add the "client_email," and click "Send"
* May receive an email with the subject "Delivery Status Notification (Failure)" and the message "Address not found" from mailer-daemon@google.com
* Delete Rows 2 to 1000, and enter Date / Time, CPU Usage %, Temperature C to header cells
* This deletion is not necessary with the improved [rpi_worksheet.py](/lesson7/rpi_worksheet.py) and [cpu_worksheet.py](/lesson7/cpu_worksheet.py) that can check the next empty row to write data

## Run cpu_spreadsheet.py with the JSON key file in a demo folder
* Edit cpu_spreadsheet.py to add .json file name
```sh
$ nano rpi_spreadsheet.py
```
> GDOCS_OAUTH_JSON = 'cpudata-xxxxxxxxxxxx.json'

> GDOCS_SPREADSHEET_NAME = 'cpudata'

* Run rpi_spreadsheet.py
```sh
$ python3 rpi_spreadsheet.py
```
![sheets-terminal](https://user-images.githubusercontent.com/45573682/166174904-8690c546-58de-4cef-99b2-ddaa4b80c735.png)

![google-sheets](https://user-images.githubusercontent.com/45573682/166174906-df2e53df-9c23-41a6-b6ac-602212e5346a.png)
