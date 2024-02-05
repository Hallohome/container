Vaultwarden:

docker run -d --name vaultwarden-2 --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx -e ADMIN_TOKEN=xxxxxxxxxx -v /share/Container-shares/vaultwarden:/data/ vaultwarden/server:latest
docker run -d --name vaultwarden-4 --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:17 --restart always -e SIGNUPS_ALLOWED=false -e WEBSOCKET_ENABLED=true -e DOMAIN=https://vault.xxxx.xx -e SMTP_HOST=xxxx.de -e SMTP_FROM=vault@xxxx.xx -e SMTP_PORT=465 -e SMTP_SECURITY=force_tls -e SMTP_USERNAME=xxxx@xxxx.xx -e SMTP_PASSWORD=xxxxxx -v /share/Container-shares/vaultwarden:/data/ vaultwarden/server:latest
