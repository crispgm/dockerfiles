# Dockerfile for Shadowsocks

## Config

Shadowsocks configuration file is `etc/shadowsocks.json`, in which `server_port`, `local_port` might be set. However, reseting `password` is REQUIRED.

## Build

```
docker build -t crisp/shadowsocks
```

## Run

```
docker run --name ssserver -d -p 2967:2968 crisp/shadowsocks
```

## Credit

Thanks to the courage of @clowwindy and his prominent work on Shadowsocks, we can get to the real internet more easily.
