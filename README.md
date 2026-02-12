# MySQL-Task-7
**CREATES DATABASE**
create database imdb;
use imdb;

**CREATES MOVIE TABLE**
create table movie
(movie_id int primary key, title varchar(100), release_year int);

**CREATES MEDIA TABLE**
create table media
(media_id int primary key, movie_id int,
media_type varchar(50),
media_url varchar(250),
foreign key (movie_id) references movie(movie_id));

**CREATES GENRE TABLE**
create table genre
(genre_id int primary key, genre_name varchar(50));

**CREATES MOVIE GENRE TABLE**
create table movie_genre
(movie_id int, genre_id int, primary key (movie_id, genre_id),
foreign key(movie_id) references movie(movie_id),
foreign key(genre_id) references genre(genre_id));

**CREATES USER TABLE**
create table user_account
(user_id int primary key, user_name varchar(100));

**CREATES REVIEW TABLE**
create table review
(review_id int primary key, movie_id int, user_id int, rating int,
review_text varchar(500),
foreign key(movie_id) references movie(movie_id),
foreign key(user_id) references user_account(user_id));

**CREATES ARTIST TABLE**
create table artist
(artist_id int primary key, artist_name varchar(100));

**CREATES SKILL TABLE**
create table skill
(skill_id int primary key, skill_name varchar(50));

**CREATES ARTIST SKILL TABLE**
create table artist_skill
(artist_id int, skill_id int, primary key (artist_id, skill_id),
foreign key (artist_id) references artist(artist_id),
foreign key (skill_id) references skill(skill_id));

**CREATES ROLE TABLE**
create table role
( role_id int primary key, role_name varchar(100));

**CREATES MOVIE ARTIST ROLE TABLE**
create table movie_artist_role
( movie_id int, artist_id int, role_id int,
primary key(movie_id, artist_id, role_id),
foreign key (movie_id) references movie(movie_id),
foreign key (artist_id) references artist(artist_id),
foreign key (role_id) references role(role_id));

**INSERT MOVIES**
insert into movie (movie_id, title, release_year) values
(1, 'Padaiyappa', 2000),
(2, 'Thug Life', 2001);

**INSERT MEDIA**
insert into media (media_id, movie_id, media_type, media_url) values
(1, 1, 'image', 'Padaiyappa-Poster.jpg'),
(2, 1, 'video', 'Padaiyappa-Trailer.mp4'),
(3, 2, 'image', 'Thug Life-Poster.jpg'),
(4, 2, 'video', 'Thug Life-Trailer');

**INSERT GENRES**
Insert into genre (genre_id, genre_name) values
(1, 'Action'),
(2, 'Comedy');

**INSERT MOVIE GENRES**
insert into movie_genre (movie_id, genre_id) values
(1, 1),
(1, 2),
(2, 2);

**INSERT USERS**
insert into user_account(user_id, user_name) values
(1, 'Senthil'),
(2, 'Kumar');

**INSERT REVIEWS**
insert into review(review_id, movie_id, user_id, rating, review_text) values
(1, 1, 1, 8, 'Movie is Good'),
(2, 1, 2, 7, 'Good Story'),
(3, 2, 1, 5, 'Funny Movie'),
(4, 2, 2, 1, 'Bad Movie');

**INSERT ARTISTS**
insert into artist (artist_id, artist_name) values
(1, 'KS Ravi Kumar'),
(2, 'Mani Rathnam');

**INSERT SKILLS**
insert into skill (skill_id, skill_name) values
(1, 'Actor'),
(2, 'Singer'),
(3, 'Producer'),
(4, 'Director');

**INSERT ARTIST SKILLS**
insert into artist_skill (artist_id, skill_id) values
(1, 1),
(1, 3),
(1, 4),
(2, 3),
(2, 4);

**INSERT ARTIST ROLES**
insert into role (role_id, role_name) values
(1, 'Guest Role'),
(2, 'Director');

**INSERT MOVIE ARTIST ROLES**
insert into movie_artist_role (movie_id, artist_id, role_id) values
(1, 1, 1),
(1, 2, 2),
(2, 1, 1);












