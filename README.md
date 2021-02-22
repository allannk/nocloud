# Nocloud
Building scripts for personal cloud systems

Service Structure
-----------------

Raspberry Gateway:
- VPN:
    - Wireguard  
- Portainer
  - Pihole            (pihole.norgaard.cc)
  - Proxy:
    - Traefik       (hall.norgaard.cc)
    - Authelia      (auth.norgaard.cc)

Heavy Server:
- File service      (drive.norgaard.cc)
    - Nextcloud
    - Postgres
    - Nginx
- Photoprism        (photo.norgaard.cc)

Future:
- WOL service
- Bitwarden (cred.norgaard.cc)

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

