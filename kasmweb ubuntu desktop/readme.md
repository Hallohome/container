Kasmweb Ubuntu Desktop_

User : kasm_user

docker run --name ubuntu-desktop-2 -it --network=qnet-static-eth0-xxxx--restart=always --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:16 --shm-size=512m -e VNC_PW=xxxx kasmweb/desktop:1.12.0