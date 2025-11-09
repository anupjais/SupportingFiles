```
docker run --rm -it busybox sh
```

```
hostname
```

```
ping google.com
```

```
ifconfig
```

```
exit
```

```
docker network
```

```
docker network inspect <network-name>
```

```
docker network create <network-name>
```

```
docker run --network <network-name> --name <container-name>
```

```
docker network connect <network-name> <container-name>
```

```
docker network disconnect <network-name> <container-name>
```

```
docker network rm <<network-name>
```

```
docker network ls
```

```
docker network ls
```


```
docker exec -it container2 ping container1
```

## To create our owm mac-address

```
docker network create -d macvlan \
--subnet=192.168.1.0/24 \
--gateway=192.168.1.1 \
-p parent=eth0 my-macvlan
```
