# ViTunes

ViTunes lets you control and navigate iTunes from the comfort of Vim.

[screenshots]

Benefits:

* Control iTunes without leaving Vim, where one is probably in a state of productive bliss
* Avoid using the mouse or trackpad; keystrokes get you there faster
* Zen-minimalist textual UI works better on small screens than iTunes' bulky, multi-paned GUI
* Control iTunes from another computer over ssh, across the room or across the world
* Let multiple people control one instance of iTunes over ssh ([how][multi]) 
* Control iTunes from a GNU/Linux client computer over ssh 

[multi]:https://github.com/danchoi/vitunes/wiki

ViTunes is pronounced vee-eye-tunes.

If you're looking for `vitunes` for MPlayer by Ryan Flannery, click [here](http://freshmeat.net/projects/vitunes).

## Prerequisites

* Ruby 1.8.6 or higher (developed on Ruby 1.9.2)
* OS X (tested on Snow Leopard 10.6)
* Vim 7.2 or higher (tested on Vim 7.3)

## Install

    gem install vitunes && vitunes-install

`vitunes-install` installs a Vim plugin into your ~/.vim/plugin directory.  If
you don't want to install the Vim plugin and just want to run `vitunes` as a
stand-alone program, just run `gem install vitunes` and skip `vitunes-install`.

If you get an error message saying that vitunes-install is missing, then you
probably have a `PATH` issue. Try one of these workarounds:

* Put the directory where Rubygems installs executables on your `PATH`
* Try installing with `sudo gem install vitunes && vitunes-install`

To upgrade ViTunes to a newer version, just repeat the installation procedure.

## How to use it 

For all the commands below, the mapleader is just assumed to be a `,`. If your
mapleader is `\` or something else, use that instead.


### Starting ViTunes

You can run ViTunes in two ways:

* within Vim with `,i` or `,I` 
* from the command line with the `vitunes` command

### General commands

* `,i` invoke or dismiss ViTunes 
* `,I` invoke ViTunes and go full screen with it
* `,?` show help and commands

`,I` is useful if you want to launch immediately into ViTunes after starting Vim.

### Navigation

* `,s` search iTunes library by search query
* `,p` select playlist
* `,a` select artist
* `,g` select genre
* `,A` select album
* `ENTER` start playing a track under cursor

Playlist, artist, genre, and album navigation (but not search) use make use of
Vim autocompletion. Start typing the first few letters of what you want. For
example, if you want to jump to all artists that start with the letter 'P',
type 'P' and you'll see the drop-down items update. This autocompletion is
case-sensitive.

`CTRL-p` and `CTRL-n` let you navigate the drop-down matches. Press `ENTER` to select
one.

More advanced autocompletion tips:

* `CTRL-e` closes the match list and lets you continue typing
* `CTRL-u`: when the match list is active, cycles forward through the match
  list and what you've typed so far; when the match list is inactive, erases
  what you've typed.
* both `TAB` and `CTRL-x CTRL-u` reactivates autocompletion if it's gone away
* `CTRL-y` selects the highlighted match without triggering ENTER

To exit the autocompletion or search query mode, press `ENTER` when the query
line is blank, or try `ESC` then `q`. 

### Volume Control

* `+` louder
* `-` softer
* `=` louder

### Playhead

* `SPACEBAR` play/pause
* `>` next track in ViTunesBuffer
* `<` previous track in ViTunesBuffer
* `>>` next track in iTunes current playlist
* `<<` previous track in iTunes current playlist
* `.` show current track and playlist, if any

One thing to note: if you start playing a track that you've gotten to by going
through the playlist dropdown, iTunes will play in continuous mode, where the
next track in the playlist will automatically start playing after the current
one ends.

But if you start playing a track you found some other way (e.g. via search
query), iTunes will stop playing after that track ends.

If you want to use ViTunes to find and queue a bunch of tracks and have them play 
in automatic succession, use the next feature...

### Copying and deleting tracks

* `,c` copy track(s) to a playlist
* `BACKSPACE` deletes track(s) from the playlist

To copy tracks, put the cursor on a track or select a range of tracks,
and then hit `,c` to select a playlist to copy them to. The tracks will be
added to the end of the playlist.

If this target playlist is already playing, you can keep queuing tracks to it
and let the mix play out automatically.

To delete tracks from a playlist, put the cursor on a track or select a range
of tracks, and then hit `BACKSPACE` (the Apple delete key) to remove them from
the playlist that you are looking at. 

### Managing playlists

* `,P` goes to the current playlist, if there is one
* `:NewPlaylist [new playlist name]` creates a new playlist

### Tips

If you want to see your entire library in a Vim buffer, load the `Library`
playlist. It may take a few seconds to load your entire iTunes library. But
once it's loaded you'll be able to page through it at blazing speed and play
any tracks you want. The list will be sorted by artist.

If you have cheap Linux netbooks, they make good ViTunes controllers.  I
control the iTunes on my Mac Mini from two Linux Asus 1015PEM netbooks that I
move around the apartment.

### History and future

I've been interested in designing alternative user interfaces to iTunes since
2008, when I was working out of the creative hacker cooperative [Betahouse](http://betahouse.org/).  

* My first experiment was [itunes-rails](http://code.google.com/p/itunes-rails/). 
* My second experiment was [itunes-command](http://danielchoi.com/software/itunes-command.html).
* ViTunes is the third experiment.

If you run a coffeeshop or coworking space where you'd like to let people use a
common iTunes library like a jukebox, **please let me know**, because I'm
interested in making something convenient for this kind of environment.  This
will probably require interaction via mobile devices.

### Buy more music, support the ViTunes project

* `,z` opens Amazon's MP3 Store in your web browser 

At no additional cost to you, Amazon will give the ViTunes developer a small
referral bonus (around 6%) when you buy MP3s via `,z`.  Thank you for your support!


## Bug reports and feature requests

Please submit these at either of these places:

* <https://github.com/danchoi/vitunes/issues>
* <http://groups.google.com/group/vitunes-users>

## About the developer

My name is Daniel Choi. I specialize in Ruby, Rails, MySQL, PostgreSQL, and iOS
development. I am based in Cambridge, Massachusetts, USA, and the little
software company I run with Hoony Youn is called [Kaja Software](http://kajasoftware.com). 

* Company Email: info@kajasoftware.com
* Twitter: [@danchoi][twitter] 
* Personal Email: dhchoi@gmail.com  
* My Homepage: <http://danielchoi.com/software>

[twitter]:http://twitter.com/#!/danchoi


