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
