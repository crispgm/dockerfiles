# Dockerfile for Shadowsocks

## Build

```
docker build -t crisp/shadowsocks
```

## Run

```
docker run --name ssserver -d -p 2967:2968 crisp/shadowsocks
```
