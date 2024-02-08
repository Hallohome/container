QBITTORRENT:

1. docker run -it --restart always --name=docker-openvpn-client-qb --cap-add=NET_ADMIN -p 8073:8073 -p 56056:56056/tcp -p 56056:56056/udp -e FIREWALL_VPN_INPUT_PORTS=56056 -e VPN_SERVICE_PROVIDER=mullvad -e VPN_TYPE=openvpn -e OPENVPN_USER=xxxxxxxxxxxx -e SERVER_COUNTRIES=Switzerland qmcgaw/gluetun
2. docker run -d --name=qbittorrent --net=container:docker-openvpn-client-qb -e PUID=1006 -e PGID=100 -e TZ=Europe/Berlin -e WEBUI_PORT=8073 -v /share/Container-shares/qb/config:/config -v /share/Container-shares/qb/downloads:/downloads --restart unless-stopped lscr.io/linuxserver/qbittorrent:latest
