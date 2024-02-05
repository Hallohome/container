Thunderbird:

(die Config liegt im -v versteckt nur via mc)
apt-get update
apt-get upgrade
(/usr/bin/firefox)

Thunderbird - Beabeiten - Einstellungn - Erweitert - Allgemein - Konfiguration bearbeiten - "Ich bin mir der Gefahren bewusst" bestätigen
network.protocol-handler.warn-external.http > true
network.protocol-handler.warn-external.https > true

docker run  --restart always --name=thunderbird-4 --shm-size="2GB" -d -e TZ=Europe/Berlin -e LANG="de_DE.UTF-8" -e LANGUAGE="de_DE:de" -e KEYBOARD=de-de-qwertz -e PUID=0 -e PGID=0 --network=qnet-static-eth0-xxxx --ip xxx.xxx.xxx.xxx --mac-address=02:42:c0:a8:fa:10 -v /share/Container-shares/thunderbird:/config kebles/wanderbird
