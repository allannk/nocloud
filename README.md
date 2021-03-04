# Nocloud
Building scripts for personal cloud systems

Service Structure
-----------------

## Gateway
Hardware:
- Raspberry Pi 4 (4gb)
- 16gb sd card for rootfs, readonly
- 256gb ssd for edge data store

Docker services:
  - wireguard
  - pihole              (pihole.norgaard.cc)
  - reverse-proxy
    - traefik           (hall.norgaard.cc)
    - authelia          (auth.norgaard.cc)

Future services:
  - simple fileshare    (share.norgaard.cc)
  - IOT controller      (iot.norgaard.cc)
  - bitwarden           (cred.norgaard.cc)

## Light Server
Hardware:
- Mediacenter PC
- 1tb old hdd for rootfs
- 2tb old hdd for media
- 2 x 4tb hdd for data (btrfs, raid 1)

Docker services:
- file service      (drive.norgaard.cc)
    nextcloud, postgres, nginx
- photoprism        (photo.norgaard.cc)

Future services:
- WOL service
