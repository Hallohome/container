Jdownloader:

GeneralSettings: Browser Command Line -> ["/usr/bin/chromium-browser", "--no-sandbox", "%s"]
BrowserCaptchaSolver: Browser Commandline -> ["/usr/bin/chromium-browser", "--no-sandbox", "%s"]
apk add chromium

https://hub.docker.com/r/jlesage/jdownloader-2
https://hub.docker.com/r/qmcgaw/gluetun

docker run -d --name=jdownloader-2-4  --shm-size 2g --net=container:docker-openvpn-client-jd -e USER_ID=0 -e GROUP_ID=0 -v /share/Container-shares/jdownloader:/config:rw -v /share/Download/JdownloaderDocker:/output:rw jlesage/jdownloader-2
docker run -it --restart always --name=docker-openvpn-client-jd --cap-add=NET_ADMIN -p 49167:5800 -p 49166:5900 -e VPN_SERVICE_PROVIDER=mullvad -e VPN_TYPE=openvpn -e OPENVPN_USER=xxxxxxxxxxxx -e SERVER_COUNTRIES=Switzerland qmcgaw/gluetun

