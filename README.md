# Nocloud
Building scripts for personal cloud systems

Services
--------

Gateway:
- Wireguard
- Traefik
- Authelia

Server:
- File service
    - Nextcloud
    - Postgres
    - Nginx
- Photoprism
- Bitwarden
- Portainer

# Docker setup
--------------




# Nextcloud
-----------

Configuration:
- Modify `docker-compose.yml` to reflect data storage directory
- Install secrets in $nocloud/secrets: `db_user` and `db_pass`

File permissions:
For now, it is acceptable that files are owned by docker/nextcloud in a way, 
that makes them virtually unbrowsable. A user should be create to allow browsing:

``` (UNTESTED)
    groupadd -u 82 nextcloud-data
    usermod -aG 82 allan
```
This, or create a new user with correct permissions, and browse with `su nc-data`

