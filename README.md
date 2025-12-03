# warp-proxy

Docker image to run Cloudflare Warp in proxy mode.

## Usage

```
docker compose up -d
```

SOCKS5 proxy server will be listening at port 40000.

## Test

### Remote DNS node
```bash
curl https://www.cloudflare.com/cdn-cgi/trace/ -x socks5h://127.1:40000
```

### Local dns mode
```bash
curl https://www.cloudflare.com/cdn-cgi/trace/ -x socks5://127.1:40000
```

# HTTP mode
```bash
curl https://www.cloudflare.com/cdn-cgi/trace/ -x http://127.1:40000
```

```bash
...
sni=plaintext
warp=on
# 👆wrap on！
gateway=off
...
```