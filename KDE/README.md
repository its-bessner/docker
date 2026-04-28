# KDE Desktop
Dieses Image stellt einen KDE Desktop bereit.

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