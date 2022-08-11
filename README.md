# one-line-commands


## Database



### mysql login

```shell
$ mysql -h{mysql_host} -P{mysql_port} -u{msyql_username} -p{mysql_password}
```

### mysql tcpdump

```shell
# tcpdump -s 0 -l -w - host {mysql_host_ip} and port {mysql_port} | strings
```

