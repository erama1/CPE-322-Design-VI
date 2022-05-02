# Lab 9 - YANG

## Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 9
## Install pyang and PlantUML
### On Raspbery Pi
```sh
$ sudo apt install libxml2-dev libxslt1-dev
$ sudo pip3 install -U lxml pyang
$ sudo pip3 install -U plantuml
```

## copy ~/iot/lesson9/intrusiondetection.yang to ~/demo
```sh
$ cp ~/iot/lesson9/intrusiondetection.yang ~/demo
$ cd ~/demo
```

## Run pyang to generate intrusiondetection.yin and intrusiondetection.uml
```sh
$ cat intrusiondetection.yang
$ pyang -f yin -o intrusiondetection.yin intrusiondetection.yang
$ cat intrusiondetection.yin
$ pyang -f uml -o intrusiondetection.uml intrusiondetection.yang --uml-no=stereotypes,annotation,typedef
$ cat intrusiondetection.uml
```

## Run PlantUML to generate intrusiondetection.png
* Install and run GIMP and Pinta to display a PNG file via VNC Viewer
* Alternativly, run SSH -Y to enable X11 forwarding on macOS with XQuartz or on Windows with Xming
```sh
$ python3 -m plantuml intrusiondetection.uml
$ cd
$ sudo apt update
$ sudo apt install gimp pinta
$ cd ~/demo
$ pinta intrusiondetection.png
$ gimp -h
$ gimp -a intrusiondetection.png
```
