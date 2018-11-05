# traefik_test
Quick &amp; dirty test of traefik with docker-compose


## USAGE


Clone repo and change dir to traefik_test directory to run commands.

```console
$ git clone https://github.com/dj4ngo/traefik_test.git
$ cd traefik_test
```

Add www.mydomain.com to localhost in  /etc/hosts

### 1. Run traefik

We will run traefik only

```console
$ docker-compose up -d traefik
```
=> Web interface : http://localhost:8082


### 2. Run one web server

Then we run only one web server, and test it using curl.

```console
$ docker-compose up -d nginx
```
=> Test it : curl -H Host:www.mydomain.com http://127.0.0.1:8081

=> Final adress : http://www.mydomain.com:8081/

### 3. Scale servers


Finally we will scale web server and perform several checks to see hostname changing thanks to load-balancing.

```console
$ docker-compose up -d --scale nginx=2  
```


### 4. Stop & rm

```console
$ docker-compose rm 
$ docker-compose rm 
```
