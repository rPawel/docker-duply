## Info
Simple duply container allowing easy backup and fetching

## Simple usage
### cli
`docker run -v "$PWD:/mnt" -v ~/.duply:/root/.duply -v "/tmp:/root/.cache" --rm=true rpawel/duply:trusty duply <profile-name> fetch <src> /mnt/<dest> [<age>]`

### docker-compose.yml

```
duply:
  image: rpawel/duply:trusty
  volumes:
    - "./:/mnt"
    - "~/.duply:/root/.duply"
    - "/tmp:/root/.cache"
  hostname: duply
  environment:
    CTNR_LOCALE: "en_GB.UTF-8"
    CTNR_TIMEZONE: "Europe/London"
  restart: unless-stopped
  tty: true
```
