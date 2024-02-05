# docker
https://www.composerize.com/


# INFO:

# QNAP:
Erst muss über die Container Station ein belibiger Docker Container installiert werden. 
Die Netzwerkkarte muss bei der Erstellung unter "Advanced" in den Modus "Bridge" gestellt werden (Irgend eine IP vergeben).
Nach der Erstellung kann dieser Container wieder gelöscht werden.

Danach via SSH am Qnap anmelden und folgenden Befehl ausführen:
"docker network ls"

Ergebnis: (bei mir)
"xxxxxx	qnet-static-eth0-xxxx	qnat	local"

Dies ist der zu verwendende Lokale Adapter.

# User Möglichkeiten für Docker 
User (dockeruser anlegen) ssh qnap "id dockeruser": UID 1006 GID 100

Qnap User:
--user 1006:100

Admin:
-e USER_ID=0

MAC
https://www.browserling.com/tools/ip-to-hex
immer mit 02:42 danach IP in HEX
--mac-address=02:42:c0:a8:fa:15