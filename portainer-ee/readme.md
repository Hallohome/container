Portainer:

docker pull portainer/portainer-ee:latest
docker run -d -p 49155:8000 -p 49154:9000 -p 49153:9443 --name portainer-ee-2 --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v /share/Container-shares/portainer-ee:/data portainer/portainer-ee:latest

Lizenz: 2-q8pk2kJWgqcZP5LN1y5RNdAgz4ocPjDIYOXFhFtpeY+WWkR0l16Qo1NajGEx5rOhGDYubgS7utTdV+zgG2G62A==
 