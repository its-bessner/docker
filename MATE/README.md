# MATE
Dieses Image stellt einen MATE Desktop bereit.

Das Image kann sonst nicht viel und ist ein bisschen
buggy.

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