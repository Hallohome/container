nginx-proxy-manager:

Add users to the Authorization tab.
Two options:
    Enable the Satisfy All switch and keep the Access tab empty.
    Disable the Satisfy All switch and add an allow all rule in the beginning of the Access tab.
Re-save the affected proxy host(s).
Bei Bad Gateway am Login: Stop container > start container > username: admin@example.com pwd: changeme >> danach normal anmelden

docker run -d --name=nginx-proxy-manager-3 --mac-address=02:42:c0:a8:fa:15 --network=qnet-static-eth0-xxxx --restart=always --ip xxx.xxx.xxx.xxx -v /share/Container-shares/nginx-proxy-manager/data:/data -v /share/Container-shares/nginx-proxy-manager/letsencrypt:/etc/letsencrypt jc21/nginx-proxy-manager
