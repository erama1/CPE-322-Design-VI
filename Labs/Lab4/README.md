# Lab 4 - Django and Flask

## Study the GitHub [repository Lesson 4](https://github.com/kevinwlu/iot/tree/master/lesson4) labs
## Installation
### 1. Install Django and Django REST framework
```sh
$ pip3 -V
$ pip3 list
$ sudo pip3 install -U setuptools
$ sudo pip3 install -U django
$ sudo pip3 install -U djangorestframework
```
![setuptool-django](https://user-images.githubusercontent.com/45573682/166134364-667e316f-a1a0-49ed-b595-adefe88d4fba.png)

```sh
$ sudo pip3 install -U django-filter
$ sudo pip3 install -U markdown
$ sudo pip3 install -U requests
```
![markdwon-requests](https://user-images.githubusercontent.com/45573682/166134398-5935efc6-9929-4576-846f-56fdcb682f73.png)

### 2. Install MariaDB server and client on Raspberry Pi
### By default, Django uses [SQLite](https://en.wikipedia.org/wiki/SQLite)
```sh
$ sudo apt update
$ sudo apt install mariadb-server mariadb-client
$ sudo apt install python3-mysqldb
$ sudo pip3 install -U mysqlclient
```
![mariadb](https://user-images.githubusercontent.com/45573682/166134527-3fe12a8b-466d-4c76-abce-3221ca511de1.png)

```sh
$ sudo mysql_secure_installation
Enter current password for root (enter for none): 
Change the root password? [Y/n] 
New password: PASSWORD
Re-enter new password: PASSWORD
Remove anonymous users? [Y/n] 
Disallow root login remotely? [Y/n] 
Remove test database and access to it? [Y/n] 
Reload privilege tables now? [Y/n]
```
## Start Django project ["stevens,"](https://github.com/kevinwlu/iot/tree/master/lesson4/stevens) run server, and view app 

<img src="https://user-images.githubusercontent.com/45573682/166138468-77c56985-f87d-4672-aa96-fe9f8c13986b.png" alt="Django Login" title="Django Login" width="50%">

<img src="https://user-images.githubusercontent.com/45573682/166138465-b42a5c65-3763-4dee-b269-840098437d93.png" alt="data-input" title="data-input" width="70%">

<img src="https://user-images.githubusercontent.com/45573682/166138454-e2ce8122-4a9c-46b4-a59c-576c7107e071.png" alt="weather-station" title="weather-station" width="70%">

## Start Django REST project "mycpu," run server, and view app

<img src="https://user-images.githubusercontent.com/98679243/161451991-199d21a0-6756-4385-9cb6-23539b4f87ce.png" alt="location-data" title="location-data" width="70%">

<img src="https://user-images.githubusercontent.com/98679243/161451995-f0584590-f19c-4126-9c23-a4d0f9c89fa2.png" alt="location-data" title="location-data" width="70%">

<img src="https://user-images.githubusercontent.com/98679243/161451999-896e4987-0eb1-4645-a0b9-661db7e429e9.png" alt="location-data" title="location-data" width="70%">

<img src="https://user-images.githubusercontent.com/98679243/161452002-1a7b48b0-529e-4ef7-a91a-860b3a280dbb.png" alt="location-data" title="location-data" width="70%">

<img src="https://user-images.githubusercontent.com/98679243/161452010-ee72daff-73a0-4275-b983-2d8ff3e34e29.png" alt="location-data" title="location-data" width="70%">

## If necessary, install Flask
## Run Flask server via hello_world.py and view app

* Run Flask server and open a browser via VNC Viewer and go to http://127.0.0.1:5000/
```sh
$ cd ~/iot/lesson4
python3 hello_world.py
```
<img src="https://user-images.githubusercontent.com/98679243/161452032-79b29517-1f0f-4532-9947-2698f7f72769.png" title="location-data">

<img src="https://user-images.githubusercontent.com/98679243/161452036-f41fc505-3a70-4202-be2b-2b0e7dc027ee.png" alt="location-data" title="location-data">
