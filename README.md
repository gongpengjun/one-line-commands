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

### os kernel version

```shell
uname -a
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

### Influxdb database list

```shell
curl -s -XPOST 'http://{INFLUXDB_HOST}:{INFLUXDB_PORT}/query?u={INFLUXDB_USERNAME}&p={INFLUXDB_PASSWORD}' --data-urlencode 'q=SHOW DATABASES' | jq
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

### maven dependency tree

```shell
mvn --settings ~/.m2/settings.xml dependency:tree
```

### maven dependency of a package

```
mvn dependency:tree -Dincludes=io.dropwizard.metrics:metrics-jetty9
```

## 6、Clojure

### generate pom.xml

```shell
lein pom
```

