wikijs:

docker run -d --restart always --name=wikijs-2 --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:0f -e PUID=1006 -e PGID=100 -e TZ=Europe/Berlin -v /share/Container-shares/wikijs/config:/config -v /share/Container-shares/wikijs/data:/data lscr.io/linuxserver/wikijs:latest