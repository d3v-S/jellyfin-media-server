# jellyfin-media-server
Contains docker-compose file for media server.
Bare minimum working set up for jellyfin based media server


## Components

### Jellyfin:
- web interface like netflix.

### Sonarr/Radarr
- look for tvseries(sonarr) and movies(radarr) over torrents.

### jackett
- provides list of indexers, which are used by sonarr and radarr

### transmission
- used to download torrent



## Procedure:








##### References:
- Helpful Repo: https://github.com/420m/dockyard  https://github.com/IronicBadger/ansible/blob/master/roles/epsilon/files/opt/docker-compose.yml
- Attaching jackett to sonarr/radarr : https://unraid-guides.com/2021/01/17/how-to-add-all-indexers-from-jackett-to-sonarr-and-radarr/#:~:text=Adding%20all%20Jackett%20indexers%20to,but%20one%20can%20be%20ignored.
