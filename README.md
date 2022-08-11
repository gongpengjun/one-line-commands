# one-line-commands


## 1、OS

### ubuntu version check

```shell
cat /etc/os-release
```

### centos version check

```shell
cat /etc/centos-release
```

## 2、Database

### mysql login

```shell
mysql -h{MYSQL_HOST} -P{MYSQL_PORT} -u{MYSQL_USERNAME} -p{MYSQL_PASSWORD}
```

### mysql tcpdump

```shell
tcpdump -s 0 -l -w - host {mysql_host_ip} and port {mysql_port} | strings
```

## 3、TCP

### tcp port listener process

```shell
lsof -nP -sTCP:LISTEN -iTCP:{PORT}
```

### process listen ports

```shell
lsof -a -i -n -P -sTCP:LISTEN -p {PID}
```

## 4、HTTP

### tcpdump http traffics

```shell
tcpdump -A -s 0 'host {HTTP_HOST} and tcp port {HTTP_PORT} and (((ip[2:2] - ((ip[0]&0xf)<<2)) - ((tcp[12]&0xf0)>>2)) != 0)'
```

## 5、Java

### find java process

```shell
jps -mlv
```

