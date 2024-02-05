Heimdall:

/config/www/.env >> APP_NAME
docker run -d --name=heimdall-4 -e PUID=1006 -e PGID=1000 -e TZ=Europe/Berlin --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:0d -v /share/Container-shares/heimdall/config:/config --restart always --shm-size="256m" lscr.io/linuxserver/heimdall:latest
