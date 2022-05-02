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
![hash-py](https://user-images.githubusercontent.com/45573682/166202108-99be3f76-ec2e-4089-b1ac-b93e180beeb0.png)

## Run snakecoin.py
### [Build the tiniest blockchain](https://medium.com/crypto-currently/lets-build-the-tiniest-blockchain-e70965a248b) in [less than 50 lines of Python](https://gist.github.com/aunyks/8f2c2fd51cc17f342737917e1c2582e2) by [Gerald Nash](https://github.com/aunyks) (2017-07-16)
```sh
$ cd ~/iot/lesson10
$ cat snakecoin.py
$ python3 snakecoin.py
```
![snakecoin-py](https://user-images.githubusercontent.com/45573682/166202129-1965848a-4730-47cf-9cbe-f25b72e13879.png)

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
![terminal1](https://user-images.githubusercontent.com/45573682/166202384-09e6db17-f570-4197-9285-cb05b557a9d2.png)

#### Terminal 2: Create a transaction and mine a new block at http://127.0.0.1:5000/mine
```sh
$ curl "localhost:5000/txion" \
     -H "Content-Type: application/json" \
     -d '{"from": "akjflw", "to":"fjlakdj", "amount": 3}'
$ curl localhost:5000/mine
```
![terminal2](https://user-images.githubusercontent.com/45573682/166202401-b75cc7fc-9788-4fda-acc0-12e65d04453d.png)

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
![node-server](https://user-images.githubusercontent.com/45573682/166202360-ae58f19e-9407-41ad-9de3-61c22d897661.png)

#### Terminal 2: Run run_app.py (Press Ctrl+C to quit)
```sh
$ vncserver
$ cd ~/python_blockchain_app
$ python3 run_app.py
```
![run-app](https://user-images.githubusercontent.com/45573682/166202329-06ee3b7c-78cd-4401-84ce-fb9b8daa1aef.png)

* Via VNC viewer, open a browser on Raspberry Pi and go to YourNet running at http://127.0.0.1:5000/
* Enter content and name, click "Post," and click "Request to mine" that generate "Block #1 is mined" at http://127.0.0.1:8000/mine
* At YourNet, click "Resync" to view Block #1

![block-1](https://user-images.githubusercontent.com/45573682/166202461-8af653e2-7161-4648-932d-383e27efefac.png)
![yournet](https://user-images.githubusercontent.com/45573682/166202468-e5f215ea-e79f-4c70-8ae9-822af854d212.png)

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
![pyota](https://user-images.githubusercontent.com/45573682/166202432-9fb67d98-f703-4e3e-a117-1dac94bc9f66.png)


