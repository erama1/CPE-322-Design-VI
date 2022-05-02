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
```
![pinta-terminal](https://user-images.githubusercontent.com/45573682/166199940-073fbe29-d3b1-40bf-b978-b62c1c769e93.png)

![pinta-intrusiondetect](https://user-images.githubusercontent.com/45573682/166199954-3a7d1c19-8c99-45b3-bbbb-a939418fb82a.png)

```sh
$ gimp -h
$ gimp -a intrusiondetection.png
```
![gimp-terminal](https://user-images.githubusercontent.com/45573682/166199969-f979023e-0ec9-489a-a826-e2a1a729db05.png)

![gimp-intrusiondetect](https://user-images.githubusercontent.com/45573682/166199984-f053e9d0-38d8-4562-af41-31a3b5ab9a04.png)
