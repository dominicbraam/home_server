# home_server

A simple home server setup that uses docker to run the services on one machine. Using containers to manage the services is a lot easier than running them natively.

### Instructions

1. Make a copy of the .env.template file and rename it to .env and set the relevant variables.
2. Run each container with the command: `docker compose --env-file ../.env up -d`

*Traefik has to be started first as all other containers depend on it. Set all other relevant ENV variables.*

### Components

- Proxy -> [Traefik](https://traefik.io/)
- Ad Block and DNS -> [Pi-Hole](https://pi-hole.net/)
- Container Management -> [Portainer](https://www.portainer.io/)
- Databases -> [MariaDB](https://mariadb.org/), [PostgreSQL](https://www.postgresql.org/)
- DB Admin -> [phpMyAdmin](https://www.phpmyadmin.net/)
- Password Manager -> [Vaultwarden](https://github.com/dani-garcia/vaultwarden)
- File Server -> [Nextcloud](https://nextcloud.com/) (addons: ToDo and Calendar servers)
- File Sync -> [Syncthing](https://syncthing.net/) - not used anymore; opted for Nextcloud desktop app for easier file syncing
- Media Server -> [Plex](https://www.plex.tv/)
- NVR with AI -> [Frigate](https://frigate.video/)
- Torrent -> [Qbittorrent](https://www.qbittorrent.org/)
- MQTT -> [Mosquito](https://mosquitto.org/)
- Dashboard -> [Heimdall](https://heimdall.site/)

### Special Notes

- Ensure that the DNS records are setup in your local DNS server before setting up Traefik. The devices will need to know where to for the configured URLs.
- Nextcloud (file server) can include files from Syncthing and allow files to be available on your personal devices and the cloud. Nextcloud also offers desktop apps for Linux, MacOS and Windows for easy file syncing.

### Dashboard

![screenshot1](https://raw.githubusercontent.com/dominicbraam/home_server/main/screenshots/serv-dash_20230111.png)
