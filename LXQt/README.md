# LXQt mit Office und vim

Dieses Image stellt LXQt, einen sehr leichtgewichtigen
Desktop bereit. Als Anwendungen sind zusätzlich noch
LibreOffice und vim installiert.

## Alte Container entfernen
```
docker-compose down --remove-orphans
```

## Neuen Container starten

```
docker-compose up -d
```

## Nach Änderungen ganz neu bauen

```
docker-compose up -d --build
```