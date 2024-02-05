ADGUARD:

docker run --name AdGuardHome-3 --restart unless-stopped --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:0a -v /share/Container-shares/adguardhome/work:/opt/adguardhome/work  -v /share/Container-shares/adguardhome/conf:/opt/adguardhome/conf adguard/adguardhome