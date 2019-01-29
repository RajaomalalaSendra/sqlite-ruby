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
SELECT 
    trackid,
    tracks.name AS track,
    albums.title AS album,
    artists.name AS artist
FROM
tracks
    INNER JOIN albums ON albums.AlbumId = tracks.AlbumId
    INNER JOIN artists ON artists.ArtistId = albums.ArtistId WHERE artists.Name LIKE "AC/DC" ;
```

> Récupérer la liste des titres de l'album "Let There Be Rock" (get all the titles of the album "Let There Be Rock")

```sql
SELECT 
    tracks.name AS title,
    albums.title AS album
FROM
    tracks
    JOIN albums ON albums.AlbumId = tracks.AlbumId WHERE albums.Title LIKE "Let There Be Rock";
```

> Afficher le prix de cet album ainsi que sa durée totale (get the price of this album and the total duration)

```sql
SELECT 
    tracks.UnitPrice AS price,
    SUM(tracks.Milliseconds) AS total_duration
FROM
    tracks
    INNER JOIN albums ON albums.AlbumId = tracks.AlbumId WHERE albums.Title LIKE "Let There Be Rock";
```

> Afficher le coût de l'intégralité de la discographie de "Deep Purple" (show the whole price of the discographie "Deep Purple")

```sql
SELECT 
    SUM(tracks.UnitPrice) As total_price
FROM
    tracks
    INNER JOIN albums ON albums.AlbumId = tracks.AlbumId 
    INNER JOIN artists ON artists.ArtistId = albums.ArtistId WHERE artists.Name LIKE "Deep Purple"; 
```

> Créer l'album de ton artiste favori en base, en renseignant correctement les trois tables albums, artists et tracks
( creation of the base of the favorite artists and gibve the table album, the artist and the track)

```sql
SELECT * FROM
albums, artists, tracks WHERE artists.Name Like "Roger Norr";
```