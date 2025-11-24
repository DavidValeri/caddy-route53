
Example Docker Compose snippet to add this Caddy container to your configuration.

```
services:
  caddy:
    container_name: caddy
    restart: unless-stopped
    image: davidvaleri/caddy-route53:2.10.2
    volumes:
      - ./caddy-config:/etc/caddy
      - ./caddy-data:/data
    ports:
      - "80:80"
      - "443:443"
```

To build locally, run the following command.

```
sudo docker buildx build -t davidvaleri/caddy-route53:2.10.2 --platform linux/amd64 ./
```