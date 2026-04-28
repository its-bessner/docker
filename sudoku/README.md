# Sudoku ohne Desktop
Dieses Image stellt Gnome-Sudoku als Anwendung 
mit einer GUI aber  ohne Desktop bereit.

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