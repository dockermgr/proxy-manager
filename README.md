## 👋 Welcome to proxy-manager 🚀  

proxy-manager README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update proxy-manager
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/proxy-manager/rootfs"
git clone "https://github.com/dockermgr/proxy-manager" "$HOME/.local/share/CasjaysDev/dockermgr/proxy-manager"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/proxy-manager/rootfs/." "$HOME/.local/share/srv/docker/proxy-manager/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-proxy-manager \
--hostname proxy-manager \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-proxy-manager/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-proxy-manager/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/proxy-manager:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/proxy-manager
    container_name: casjaysdevdocker-proxy-manager
    environment:
      - TZ=America/New_York
      - HOSTNAME=proxy-manager
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-proxy-manager/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-proxy-manager/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/proxy-manager
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/proxy-manager" "$HOME/Projects/github/casjaysdevdocker/proxy-manager"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/proxy-manager"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
