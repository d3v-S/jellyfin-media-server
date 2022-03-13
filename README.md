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

- Run docker-compose yaml using ```PUID=1000 PGID=1000 MEDIA_HOME=/home/user/media/ docker-compose -f dc-ms.yaml up```
- PUID and PGID == ```id $USER```
- Once everything is up, set up Jellyfin. Pretty intuitive.
- Set up Jackett: add indexers (basically, list of sites to check for torrent, click on *Add Indexers* and select). 
- Set up Sonarr/Radarr:
  - Settings -> indexers -> + -> Torznab (custom). Put in URL of Jackett. **Set categories as TV and MOVIES** (sonarr) (Please see references)
  - Settings -> download clients -> + -> Transmission. Put in URL of Transmission.
- Since I could not make it work with one tranmission client and different download folders, I have used 2 transmission containers, exposed on 9091 and 9092 port.
- So, attach one transmission to Sonarr and other to radarr, so one downloads movies and other tv series in different folders.






##### References:
- Helpful Repo: https://github.com/420m/dockyard  https://github.com/IronicBadger/ansible/blob/master/roles/epsilon/files/opt/docker-compose.yml
- Attaching jackett to sonarr/radarr : https://unraid-guides.com/2021/01/17/how-to-add-all-indexers-from-jackett-to-sonarr-and-radarr/#:~:text=Adding%20all%20Jackett%20indexers%20to,but%20one%20can%20be%20ignored.
