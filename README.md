# THURSDAY JUNE 13th SQL LECTURE

#### Structured Query Language

Great for:

- _Persistence_ - Remembering information/data
- _Organizing data_
- _finding data in a program_

### CRUD

Ceate
Read
Update
Delete

Challenges:

1. Write the SQL to return all of the rows in the artists table

```SQL
    SELECT * FROM artists;
```

2. Write the SQL to to select the artists with the name "Black Sabbath"

```SQL
    SELECT * FROM artists WHERE name = "Black Sabbath";
```

3. Write the SQL to create a table names 'fans' with an autoincrementing ID that's primary key and a name field of type text.

```SQL
    CREATE TABLE fans (
        id INTEGER PRIMARY KEY AUTOINCREMENT,
        name TEXT
    );
```

4. Write the SQL to alter the fans tabele to have an artist_id.

```SQL
    ALTER TABLE fans ADD COLUMN artist_id INTEGER;
```

5. Write the SQL to add yourself as a fan of ~~the Black Eyed Peas? ArtistId **169**~~ Queen!

```SQL
    INSERT INTO fans (name, artist_id)
    VALUES("Kevin", 51); -- Kevin likes Queen, I do, too!
```

6. Check out the `Faker gem`, update your name to be a new fake name.

```SQL
    UPDATE fans
    SET name = "Mo"
    WHERE name = "Tony";
```

7. Find the fans who are Not a fan of the Black Eyed Peas.

```SQL
    SELECT * FROM fans WHERE artist_id <> 169;
```

8. Write the SQL to show us all the artist names and album titles.

```SQL
    SELECT artist.name, album.title FROM artists JOIN albums ON artists.id = albums.artist_id;
```

9. Write the SQL to show us the artist name, album name, and number of tracks on that album.

```SQL
    SELECT artists.name, albums.title, COUNT(tracks.name) FROM albums 
    JOIN artists ON artists.id = albums.artist_id
    JOIN tracks ON albums.id = tracks.album_id
    GROUP BY albums.title
    LIMIT 100;
```

9. Write the SQL that shows us the artist name, album name, and number of tracks on that album.

```SQL
    SELECT artists.name, albums.title, COUNT(tracks.name) FROM albums 
    JOIN artists ON artists.id = albums.artist_id
    JOIN tracks ON albums.id = tracks.album_id
    GROUP BY albums.title
    LIMIT 100;
```

10. Write the SQL to delete a fan.
```SQL
    DELETE FROM fans WHERE name = "Phil";
```