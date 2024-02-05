Calibre:

User: abc Passwort XXX

docker run -d --name=calibre-3 --security-opt seccomp=unconfined  --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:14 -e PUID=1006 -e PGID=100 -e TZ=Europe/Berlin -v /share/Container-shares/calibre/library:/config -v /share/ebooks:/mnt --restart always lscr.io/linuxserver/calibre:latest
docker run -d --name=calibre-3 --security-opt seccomp=unconfined  --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:14 -e PUID=1006 -e PGID=100 -e TZ=Europe/Berlin -e PASSWORD=XXX -v /share/Container-shares/calibre/library:/config -v /share/ebooks:/mnt --restart always lscr.io/linuxserver/calibre:latest
