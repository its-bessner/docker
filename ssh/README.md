# SSH-Terminal
Das erzeugt einen Ubuntu-Terminal Container, mit dem
man sich per SSH verbinden kann. 

User ist terminal:terminal

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