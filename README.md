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
- DB Servers -> [MariaDB](https://mariadb.org/), [PostgreSQL](https://www.postgresql.org/)
- Password Manager Server -> [Vaultwarden](https://github.com/dani-garcia/vaultwarden)
- File Server -> [Nextcloud](https://nextcloud.com/) (addons: ToDo and Calendar servers)
- File Sync Server -> [Syncthing](https://syncthing.net/)
- Media Server -> [Plex](https://www.plex.tv/)
- Torrent Server -> [Qbittorrent](https://www.qbittorrent.org/)
- Dashboard -> [Heimdall](https://heimdall.site/)

### Special Notes

- Ensure that the DNS records are setup in your local DNS server before setting up Traefik. The devices will need to know where to for the configured URLs.
- Nextcloud (file server) can include files from Syncthing and allow files to be available on your personal devices and the cloud.
