Jdownloader:

GeneralSettings: Browser Command Line -> ["/usr/bin/chromium-browser", "--no-sandbox", "%s"] </br>
BrowserCaptchaSolver: Browser Commandline -> ["/usr/bin/chromium-browser", "--no-sandbox", "%s"]</br>
apk add chromium</br>

https://hub.docker.com/r/jlesage/jdownloader-2</br>
https://hub.docker.com/r/qmcgaw/gluetun</br>

1. docker run -d --name=jdownloader-2-4  --shm-size 2g --net=container:docker-openvpn-client-jd -e USER_ID=0 -e GROUP_ID=0 -v /share/Container-shares/jdownloader:/config:rw -v /share/Download/JdownloaderDocker:/output:rw jlesage/jdownloader-2</br>

2. docker run -it --restart always --name=docker-openvpn-client-jd --cap-add=NET_ADMIN -p 49167:5800 -p 49166:5900 -e VPN_SERVICE_PROVIDER=mullvad -e VPN_TYPE=openvpn -e OPENVPN_USER=xxxxxxxxxxxx -e SERVER_COUNTRIES=Switzerland qmcgaw/gluetun</br>


QBITTORRENT:

1. docker run -it --restart always --name=docker-openvpn-client-qb --cap-add=NET_ADMIN -p 8073:8073 -p 56056:56056/tcp -p 56056:56056/udp -e FIREWALL_VPN_INPUT_PORTS=56056 -e VPN_SERVICE_PROVIDER=mullvad -e VPN_TYPE=openvpn -e OPENVPN_USER=xxxxxxxxxxxx -e SERVER_COUNTRIES=Switzerland qmcgaw/gluetun</br>

2. docker run -d --name=qbittorrent --net=container:docker-openvpn-client-qb -e PUID=1006 -e PGID=100 -e TZ=Europe/Berlin -e WEBUI_PORT=8073 -v /share/Container-shares/qb/config:/config -v /share/Container-shares/qb/downloads:/downloads --restart unless-stopped lscr.io/linuxserver/qbittorrent:latest</br>
