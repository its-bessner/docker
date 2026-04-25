# Overview 
- 
- Stellt eine statische Webseite zur Verfügung.
- Läuft auf dem Port 8081
- Port kann ggf. beim Instanziieren verbogen werden.

## Image bauen

```
docker-compose down --remove-orphans && docker-compose up -d --build 
```

## Port verbiegen

`docker-compose.yml`
```diff
ports:
- - "8081:80"
+ - "8082:80"
restart: unless-stopped
```

___Oder:___

Direkt selbst einen Container mit `-p` bauen:

```
docker run -d -p 8082:80 my_image
```

