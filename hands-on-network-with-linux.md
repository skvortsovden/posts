# Hands-On Network with Linux

## Send and receive messages with NC

What is NC?
> NC stands for **netcat** - a computer networking utility for reading from and writing to network connections using TCP or UDP. 

Listen for incoming messages:

```bash
nc -l localhost 7777 # listen for incoming traffic on localhost port 7777
```

Send message:

```bash
nc 7777 # open connection with localhost over port 7777
your_message # type any message
```

```bash
$ nc localhost 7777 # open connection
hey! # sent
```

```bash
$ nc -l localhost 7777 # listen for incoming messages
hey! # received
```


## Test connection with NC

```bash
nc -vz google.com 443
```

- **v** is verbosity level
- **z** is zero input/output mode


## Send HTTP request with NC

0. Having docker installed run http server locally:

```
docker run -it -p 80:80 -d nginx
```

1. Open connection

```bash
nc localhost 80
```

2. Send GET request

```bash
GET /index.html
```

```bash
$ nc localhost 80 # 1. Open connection
GET /index.html   # 2. Send GET request
<!DOCTYPE html>   # Response
<html>
<head>
<title>Welcome to nginx!</title>
<style>
html { color-scheme: light dark; }
body { width: 35em; margin: 0 auto;
font-family: Tahoma, Verdana, Arial, sans-serif; }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
```