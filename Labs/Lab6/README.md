# Lab 6 - Node.js and Pystache

## Study the Github [repository]() Lesson 6

## Install Node.js and run hello-world.js, hello.js, and http.js

```sh
$ node -v
$ npm -v
$ node -h
$ cd ~/iot/lesson6
$ node hello-world.js
$ node hello.js
Server running at http://127.0.0.1:8080/
response end call done
request end event fired
response end call done
request end event fired
^C
$ node http.js
0

1
2
^C
$
```

## Install Pystache and run say_hello.py that uses the template in say_hello.mustache

```
$ sudo pip3 install pystache
$ cd ~/iot/lesson6
$ cat say_hello.mustache
$ cat say_hello.py
$ python3 say_hello.py
Hi Alexa!
Hello, World!

['Hey ', _SectionNode(key='who', index_begin=12, index_end=18, parsed=[_EscapeNode(key='.'), '!'])]
Hey Google!
Hey Siri!
$
```
