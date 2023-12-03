CREATE TABLE Artists (
    artist_id INT PRIMARY KEY,
    name VARCHAR(255)
);

CREATE TABLE Albums (
    album_id INT PRIMARY KEY,
    title VARCHAR(255),
    artist_id INT,
    FOREIGN KEY (artist_id) REFERENCES Artists(artist_id)
);

CREATE TABLE Songs (
    song_id INT PRIMARY KEY,
    title VARCHAR(255),
    duration INT,
    album_id INT,
    FOREIGN KEY (album_id) REFERENCES Albums(album_id)
);

CREATE TABLE Genres (
    genre_id INT PRIMARY KEY,
    name VARCHAR(255)
);

CREATE TABLE ArtistGenre (
    artist_id INT,
    genre_id INT,
    PRIMARY KEY (artist_id, genre_id),
    FOREIGN KEY (artist_id) REFERENCES Artists(artist_id),
    FOREIGN KEY (genre_id) REFERENCES Genres(genre_id)
);

