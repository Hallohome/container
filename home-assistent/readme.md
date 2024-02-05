home Assistent:

docker run -d --name homeassistant-3 --privileged --restart=unless-stopped -e TZ=Europe/Berlin -v /share/Container-shares/homeassistant:/config --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:0b homeassistant/home-assistant:latest
