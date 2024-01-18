# home_server

A simple home server setup that uses docker to run the services on one machine. Using containers to manage the services is a lot easier than running them natively.

### Instructions

1. Make a copy of the .env.template file and rename it to .env and set the relevant variables.
2. Run each container with the command: `docker compose --env-file ../.env up -d`

*Start Traefik initially, since all other containers rely on it. Also, ensure to set all other necessary environment variables.*

### Services

- Proxy -> [Traefik](https://traefik.io/)
- Backup Handler -> [Kopia](https://kopia.io/)
- Ad Block and DNS -> [Pi-Hole](https://pi-hole.net/)
- Container Management -> [Portainer](https://www.portainer.io/)
- Databases -> [MariaDB](https://mariadb.org/), [PostgreSQL](https://www.postgresql.org/)
- DB Admin -> [phpMyAdmin](https://www.phpmyadmin.net/)
- Password Manager -> [Vaultwarden](https://github.com/dani-garcia/vaultwarden)
- File Server -> [Nextcloud](https://nextcloud.com/) (addons: ToDo and Calendar servers)
- Document Manager -> [Paperless-ngx](https://docs.paperless-ngx.com/)
- File Sync -> [Syncthing](https://syncthing.net/) - not used anymore; opted for Nextcloud desktop app for easier file syncing
- Media Server -> [Plex](https://www.plex.tv/)
- Project Management -> [Leantime](https://leantime.io/)
- NVR with AI -> [Frigate](https://frigate.video/)
- Torrent -> [Qbittorrent](https://www.qbittorrent.org/)
- MQTT -> [Mosquito](https://mosquitto.org/)
- Dashboard -> [Heimdall](https://heimdall.site/)

### Special Notes

- Before configuring Traefik, make sure to establish the DNS records on your local DNS server. For services accessible to the public, it's crucial to have an external proxy manager equipped with the correct DNS records, so that devices know where to go for the configured URLs.
- Nextcloud serves as a file server and can integrate files from Syncthing, providing access on both personal devices and the cloud. However, bear in mind that Nextcloud may not consistently read files added from external operations. eg. from Syncthing. For seamless file synchronization, Nextcloud offers desktop apps for Linux, MacOS, and Windows.

### Dashboard

![screenshot1](https://raw.githubusercontent.com/dominicbraam/home_server/main/screenshots/serv-dash_20240118.png)
