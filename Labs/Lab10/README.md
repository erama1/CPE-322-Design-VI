# Lab 10 - Bloackchain

## Study the GitHub [repository](https://github.com/kevinwlu/iot) Lesson 10
## Run hash_value.py twice and compare results
### Hash function with randomization
* Run hash_value.py twice and compare results
```sh
$ cd ~/iot/lesson10
$ cat hash_value.py
$ python3 hash_value.py
$ python3 hash_value.py
```
## Run snakecoin.py
### [Build the tiniest blockchain](https://medium.com/crypto-currently/lets-build-the-tiniest-blockchain-e70965a248b) in [less than 50 lines of Python](https://gist.github.com/aunyks/8f2c2fd51cc17f342737917e1c2582e2) by [Gerald Nash](https://github.com/aunyks) (2017-07-16)
```sh
$ cd ~/iot/lesson10
$ cat snakecoin.py
$ python3 snakecoin.py
```
## Run snakecoin-server-full-code.py on Terminal 1 and mine a new block on Terminal 2
(https://gist.github.com/aunyks/47d157f8bc7d1829a729c2a6a919c173) by Gerald Nash (2017-07-23)
#### Terminal 1: Run the SnakeCoin server at http://127.0.0.1:5000/ (Press Ctrl+C to quit)
```sh
$ cat snakecoin-server-full-code.py
$ python3 snakecoin-server-full-code.py
$ cd
```
* In case of ImportError: cannot import name 'soft_unicode' from 'markupsafe'
```sh
$ sudo pip3 install markupsafe==2.0.1
$ python3 snakecoin-server-full-code.py
```

#### Terminal 2: Create a transaction and mine a new block at http://127.0.0.1:5000/mine
```sh
$ curl "localhost:5000/txion" \
     -H "Content-Type: application/json" \
     -d '{"from": "akjflw", "to":"fjlakdj", "amount": 3}'
$ curl localhost:5000/mine
```
## Clone Python blockchain app and uncomment the last line of node_server.py
## Run node_server.py on Terminal 1 and run_app.py on Terminal 2
#### Terminal 1: Uncomment the last line (Line 257) of node_server.py (or search for port=8000) and run (Press Ctrl+C to quit)
* In the [GNU nano](https://en.wikipedia.org/wiki/GNU_nano) text editor, Ctrl+W (shown as as ^W) goes to the search menu
```sh
$ git clone https://github.com/satwikkansal/python_blockchain_app.git
$ cd ~/python_blockchain_app
$ nano node_server.py
$ python3 node_server.py
```
#### Terminal 2: Run run_app.py (Press Ctrl+C to quit)
```sh
$ vncserver
$ cd ~/python_blockchain_app
$ python3 run_app.py
```
* Via VNC viewer, open a browser on Raspberry Pi and go to YourNet running at http://127.0.0.1:5000/
* Enter content and name, click "Post," and click "Request to mine" that generate "Block #1 is mined" at http://127.0.0.1:8000/mine
* At YourNet, click "Resync" to view Block #1

## Install pyota[ccurl]
## Run iri_node_info.py
* Demonstrated on Raspberry Pi OS and Ubuntu
* [PyOTA](https://github.com/iotaledger/iota.py) (IOTA Python Client Library)
* [IRI](https://docs.iota.org/docs/node-software/1.0/overview) (IOTA Reference Implementation)

```sh
$ sudo pip3 install pyota[ccurl]
$ cd ~/iot/lesson10
$ cat iri_node_info.py
$ python3 iri_node_info.py
$ cd
```

