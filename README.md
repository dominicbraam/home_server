# home_server

A simple home server setup that uses docker to run the services on one machine. Using containers to manage the services is a lot easier than running them natively.

### Instructions

1. Make a copy of the .env.template file and rename it to .env and set the relevant variables.
2. Run each container with the command: `docker compose --env-file ../.env up -d`

*Traefik has to be started first as all other containers depend on it. Set all other relevant ENV variables.*

### Components

Proxy -> Traefik
DNS -> Pi-Hole
Container Management -> Portainer
Dashboard -> Heimdall
DB Servers -> MariaDB, PostgreSQL
File Server -> Nextcloud (addons: ToDo and Calendar servers)
File Sync Server -> Syncthing
Media Server -> Plex
Torrent Server -> Qbittorrent
Password Manager Server -> Vaultwarden
