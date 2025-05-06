# remnawave
Configs for Remnawave Panel

## XTTTP Inbound with NGINX Configuration
<details>
  <summary>
    XHTTP NGINX Configuration (To be configured on EACH Node where you want to use XHTTP and NOT Panel)
  </summary>
  ```nginx
    # gRPC Proxy
    location /VLSpdG9k {
        grpc_pass grpc://127.0.0.1:2023;
        grpc_set_header Host $host;
        grpc_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
    }
  ```
</details>
<details>
  <summary>
    XHTTP Configuration (Don't forget to replace the default values)
  </summary>
  ```json
    {
      "tag": "Give any tag you want",
      "port": 2023,
      "listen": "127.0.0.1",
      "protocol": "vless",
      "settings": {
        "clients": [],
        "decryption": "none"
      },
      "sniffing": {
        "enabled": true,
        "destOverride": [
          "http",
          "tls",
          "quic"
        ]
      },
      "streamSettings": {
        "network": "xhttp",
        "xhttpSettings": {
          "path": "/VLSpdG9k"
        },
        "realitySettings": {
          "dest": "/dev/shm/nginx.sock",
          "show": false,
          "xver": 1,
          "spiderX": "",
          "shortIds": [
            "5d3ddcaf67893d8b"
          ],
          "publicKey": "8lYLXCb8jR6Fa5jq0t5SMbZ1zQcvrmOhAe4EPoDUwmo",
          "privateKey": "vkNfSoEef0T4QWyaREhx1Lrfeq0hfyYnmmDPljKg3M0",
          "serverNames": [
            "example.com"
          ]
        }
      }
    },
  ```
</details>
<details>
  <summary>
    XHTTP Host Config
  </summary>
  ![xhttp-host-config](https://raw.githubusercontent.com/TrulyInfinite/remnawave/567cb19d6661b23c447c8c27e6a177dc326338df/assets/xhttp_host_config.jpg)
</details>
