# The Chinook of the musics
> Récupérer tous les albums (to get all the albums)

```sql
SELECT * FROM albums;
```
> Récupérer tous les albums dont le titre contient "Great" (get the album with the title "Great")

```sql
SELECT * FROM albums WHERE Title LIKE "%Great%";
```

> Donner le nombre total d'albums contenus dans la base (counting all the albums)

```sql
SELECT COUNT(albumid) FROM albums;

```

> Supprimer tous les albums dont le nom contient "music"(delete the albums contains the name "music")

```sql
DELETE  FROM albums WHERE Title LIKE "%music%";

```

> Récupérer tous les albums écrits par AC/DC (get all the album written by AC/DC)

```sql
SELECT * FROM albums JOIN artists on artists.ArtistId = albums.ArtistId WHERE Name = "AC/DC"; 
```

> Récupérer tous les titres des albums de AC/DC (get all the titles of the all the albums of AC/DC)

```sql
SELECT * FROM
albums
    INNER JOIN tracks ON albums.albumid = tracks.albumid
    INNER JOIN artists ON artists.artistid = albums.artistid WHERE   ;
```

> Récupérer la liste des titres de l'album "Let There Be Rock"

```sql
```

> Afficher le prix de cet album ainsi que sa durée totale

```sql
```

> Afficher le coût de l'intégralité de la discographie de "Deep Purple"

```sql
```

> Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables albums, artists et tracks

```sql
```