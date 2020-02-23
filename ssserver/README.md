# ss_server
A secure socks5 proxy used to  protect your Internet traffic.


# Quick Start

```bash
docker-compose up
```

```bash
docker run --name='shadowsocks' -d \
  --publish=8388:8388 \
  --env='SS_PASSWORD=ssp@ss' \
imageName:latest
```


## Available Configuration Parameters

*Please refer the docker run command options for the `--env-file` flag where you can specify all required environment variables in a single file. This will save you from writing a potentially long docker run command. Alternately you can use docker compose.*

Below is the complete list of available options that can be used to customize your shadowsocks installation.

- **SS_PASSWORD**: A password used to encrypt transfer. Defaults to `ssp@ss`.
- **SS_TIMEOUT**: Connections timeout in seconds. Defaults to `300`.
- **SS_METHOD**: The encryption method, "bf-cfb", "aes-256-cfb", etc. Defaults to `aes-256-cfb`.


# References
  * https://github.com/dockage/shadowsocks-server
  * https://github.com/shadowsocks/shadowsocks
  * https://github.com/shadowsocks/shadowsocks/wiki/Encryption
  * https://github.com/shadowsocks/shadowsocks/wiki/Configuration-via-Config-File
  * https://github.com/shadowsocks/shadowsocks/wiki/TCP-Fast-Open
