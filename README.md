---
  tags: sinatra, orm, activerecord
  languages: ruby
  resources: 2
---

# Sinatra Playlister

### Overview

In the theme of moving from simple command line application to static website to dynamic web app, it's time to move Playlister to the interwebs using Sinatra. In this lab, you'll be:

  1. Giving our "library" of songs a dynamic web interface
  2. Creating a few complex forms that allow you to create and edit Songs, Artists and Genres.

### Instructions

The first thing you should aim to do is create a Sinatra interface for the data in `db/data`. There is a `LibraryParser` class included in the `lib` folder that you may use, though it may need some tweaking to work with your specific application. Your associations should follow this pattern:

1. An Artist can have multiple songs and multiple genres
2. A Genre can have multiple artists and multiple songs
3. A Song can belong to ONE Artist and multiple genres
4. There will be a join table needed somewhere here

I should be able to visit the following routes:

1. `/songs`
  * This should present me with a list of all songs in the libaray.
  * Each song should be a clickable link to that particular song's show page.
2. `/genres`
  * This should present me with a list of all genres in the library.
  * Each genre should be a clickable link to that particular genre's show page.
3. `/artists`
  * This should present me with a list of all artists in the library.
  * Each artist should be a clickable link to that particular artist's show page.
4. `/songs/:slug`
  * Any given song's show page should have links to that song's artist and the each genre associated with the song.
5. `/artists/:slug`
  * Any given artist's show page should have links to each of his or her songs and genres.
6. `/genres/:slug`
  * Any given genre's show page should have links to each of its artists and songs.

To get the data into your database, you will want to figure out how to use your `LibraryParser` class in the `db/seeds.rb` file.

Notice that there are no forms involved yet. Get the basics of the app working first, making all of the feature specs in `spec/features/basic_view_specs.rb` pass and then move on to implementing the following features:

1. `/songs/new`
  * I should be able to create a new song
  * Genres should be presented as checkboxes
  * I should be able to enter the Artist's name in a text field (only one Artist per song.)
2. `/songs/:slug/edit`
  * I should be able to change everything about a song, including the genres associated with it and its artist.

Think about the custom writer or writers you may need to write to make these features work. Make the feature specs in `spec/features/song_form_specs.rb` pass.


### Bonus

Once you've finished, think about how you might make the app look nicer. Also, what bonus features can you implement? It'd be nice if I could, say, sort the list of songs by their name or their artist's name. Maybe I could search for an artist? The sky's the limit, really! Make sure you've gotten the basics of the application working first, though, before you approach any of these additional features.

### Extra Special Bonus

Write some controller and model specs!

### Resources
* [Sinatra Up and Running](http://books.flatironschool.com/books/101) - [Fundamentals](http://books.flatironschool.com/books/101), page 29
* [Wikipedia](http://en.wikipedia.org/) - [Clean ULR - Slugs](http://en.wikipedia.org/wiki/Slug_(web_publishing)#Slug)
