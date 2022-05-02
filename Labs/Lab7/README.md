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
* If yes, the Write API Key is saved in API_KEY.pickle
* Alternatively, replace YOURKEYHERE with the Write API in Line 10 of thingspeak_cpu_loop.py

### Sign up and log in the Google Cloud Platform Identity and Access Management [(IAM)](https://console.developers.google.com/projectselector/iam-admin/iam)
* The following rpidata project and [rpi_spreadsheet.py](/lesson7/rpi_spreadsheet.py) require Raspberry Pi and system_info.py
* Alternatively, follow the same steps for a cpudata project and run [cpu_spreadsheet.py](/lesson7/cpu_spreadsheet.py) that does not require Raspberry Pi and system_info.py

* Click "Create" and enter the project name, e.g., rpidata
* &equiv; > APIs & Services > + Enable APIs & Services > Enable both Drive API and Sheets API
* Credential > Create Credentials > Create service account key > Service account > rpidata > JSON key type > Create > download rpidata-xxxxxxxxxxxx.json

## Install gspread and oauth2client
```sh
$ sudo pip3 install -U gspread oauth2client
```
## Log in the Google Cloud Platform Identity and Access Management, create a project cpudata, enable both Drive API and Sheets API, create and download service account JSON key file
## Start a new Google sheet cpudata, share it with the client email in the JSON file, delete Rows 2 to 1000, and edit the header cells
## Run cpu_spreadsheet.py with the JSON key file in a demo folder

