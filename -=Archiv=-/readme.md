# NICHT GENUTZT

https://www.composerize.com/

### JDOWNLOADER:</br>
VYPRVPN:</br>
docker run -d --name=jdownloader-2-4  --shm-size 2g --net=container:docker-openvpn-client-3 -e USER_ID=0 -e GROUP_ID=0 -v /share/Container-shares/jdownloader:/config:rw -v /share/Download/JdownloaderDocker:/output:rw jlesage/jdownloader-2</br>

docker run -it --restart always --name=docker-openvpn-client-3 --cap-add=NET_ADMIN -p 49167:5800 -p 49166:5900 -e NETWORK=xxx.xxx.xxx.0/24 -e VPN_SERVICE_PROVIDER=vyprvpn -e OPENVPN_USER=xxxx@xxxx.xx -e OPENVPN_PASSWORD=XXXXXX -e SERVER_REGIONS=Switzerland qmcgaw/gluetun</br>


### QBITTORRENT</br>
admin / adminadmin</br>
docker run -it --restart always --name=docker-openvpn-client-qb --cap-add=NET_ADMIN -p 8073:8073 -p 56056:56056/tcp -p 56056:56056/udp -e FIREWALL_VPN_INPUT_PORTS=56056 -e NETWORK=xxx.xxx.xxx.0/24 -e VPN_SERVICE_PROVIDER=vyprvpn -e OPENVPN_USER=xxxx@xxxx.xx -e OPENVPN_PASSWORD=XXXXX -e SERVER_REGIONS=Switzerland qmcgaw/gluetun</br>

docker run -d --name=qbittorrent --net=container:docker-openvpn-client-qb -e PUID=1006 -e PGID=100 -e TZ=Europe/Berlin -e WEBUI_PORT=8073 -v /share/Container-shares/qb/config:/config -v /share/Container-shares/qb/downloads:/downloads --restart unless-stopped lscr.io/linuxserver/qbittorrent:latest</br>


### TRANSMISSION:</br>
docker run -it --restart always --name=docker-openvpn-client-tm --cap-add=NET_ADMIN -p 9091:9091 -p 51413:51413 -p 51413:51413/udp -e NETWORK=xxx.xxx.xxx.0/24 -e VPN_SERVICE_PROVIDER=vyprvpn -e OPENVPN_USER=xxxx@xxxx.xx -e OPENVPN_PASSWORD=XXXXX -e SERVER_REGIONS=Switzerland qmcgaw/gluetun</br>

docker run -d --name=transmission --net=container:docker-openvpn-client-tm -e PUID=1000 -e PGID=1000 -e TZ=Europe/Berlin -v /share/Container-shares/transmission/config:/config -v /share/Container-shares/transmission/downloads:/downloads -v /share/Container-shares/transmission/watch:/watch --restart unless-stopped lscr.io/linuxserver/transmission:latest</br>

### Homer</br>
chown -R lighttpd:www-data assets/</br>
docker run -d --name=homer-1 --user 0:0 -v /share/Container-shares/homer:/www/assets --network=qnet-static-eth0-1d4ea8 --restart=always --ip xxx.xxx.xxx.23 b4bz/homer:latest</br>

### statping</br>
docker run -d --name statping-1 --restart always --network=qnet-static-eth0-1d4ea8 --ip xxx.xxx.xxx.18 -v /share/Container-shares/statping:/app -v /mnt/HDA_ROOT/.config/stunnel/backup.cert:/app/server.crt -v /mnt/HDA_ROOT/.config/stunnel/backup.key:/app/server.key statping/statping</br>

docker run -d --name statping-1 --restart always --network=qnet-static-eth0-1d4ea8 --ip xxx.xxx.xxx.18 -v /share/Container-shares/statping:/app -v /mnt/HDA_ROOT/.config/stunnel/backup.cert:/app/server.crt -v /mnt/HDA_ROOT/.config/stunnel/backup.key:/app/server.key adamboutcher/statping-ng</br>

### webTop</br>
https://www.linuxserver.io/blog/2021-05-05-meet-webtops-a-linux-desktop-environment-in-your-browser</br>

docker run -d --name=webtop-2 -e PUID=0 -e PGID=0 -e TZ=Europe/Berlin -e LANG="de_DE.UTF-8" -e LANGUAGE="de_DE:de" -e KEYBOARD=de-de-qwertz -v /share/Container-shares/webtop:/config --shm-size="2gb" --network=qnet-static-eth0-1d4ea8 --ip xxx.xxx.xxx.17 --mac-address=02:42:c0:a8:fa:11 --restart unless-stopped ghcr.io/linuxserver/webtop</br>

### NEXUS3</br>
docker run -d --name nexus3-1 --network=qnet-static-eth0-1d4ea8 --ip xxx.xxx.xxx.14 --user 1006:100 -v /share/Container-shares/nexus3:/nexus-data sonatype/nexus3</br>

### mediaelch</br>
docker run --name=mediaelch-1 -p 49173:5800 -p 49172:5900 -v /share/Container-shares/mediaelch:/config/xdg/config/kvibes -e TZ=Europe/Berlin -e LANG="de_DE.UTF-8" -e LANGUAGE="de_DE:de" -v /share/Movies:/movies -e PGID=0 -e PUID=0 masonxx/mediaelch:latest</br>

### tinymediamanager</br>
docker run -d --name=tinymediamanager-1 -v /share/Container-shares/tinymediamanager:/config -v /share/Movies:/media -e GROUP_ID=0 -e USER_ID=0 -e TZ=Europe/Berlin -p 49171:5800 -p 49170:5900 romancin/tinymediamanager:latest-v4</br>

### KODI:</br>
https://hub.docker.com/r/fhriley/kodi-headless-novnc</br>

docker run --name kodi-headless-novnc-2 -d --network=qnet-static-eth0-1d4ea8 --ip xxx.xxx.xxx.12 --mac-address=02:42:c0:a8:fa:0c --init -e KODI_DB_HOST=xxx.xxx.xxx.3 -e KODI_DB_USER=xxxx -e KODI_DB_PASS=xxxx -v /share/Container-shares/kodi-headless-leia:/data/.kodi fhriley/kodi-headless-novnc:latest-data-2</br>
