# RADIO

## Overview
Radio is a small command line wrapper around mpc for listening to internet
radio streams with Mplayer, [MPD](http://www.musicpd.org/) or Chromecast (via [Castnow](https://github.com/xat/castnow)). The main reason I wrote it is to have command-line completion for my internet radio bookmarks.

## Installation

### Manual Installation

	git clone $REPO_URL
	cp radio/bin/radio /usr/local/bin
	cp radio/bash_completion.d/radio /etc/bash_completion.d
	cp radio/dots/radio ~/.radio

### bash-get Installation

_radio_ can be installed by [bash-get](https://github.com/werkshy/bash-get)

    bash-get install github.com/werkshy/radio

## Usage

By default `radio` will use `mplayer` for playback. See the configuration info below for how to enable MPD or Chromecast instead.

List all configured stations

    radio

    radio list

Play a station (tab completion available)

	radio STATION

Stop playing

	radio stop

## Configuration

Edit ~/.radio. The format is

    staion-name: url

Station URLs can be playlists or streams, typically shoutcast streams.

### MPLAYER

The default playback method if installed is mplayer.

### MPD

If `$MPD_HOST` is set, the playback method will be `mpc`. You can set this environment variable if `radio` is run on the same host as `mpd`:

    MPD_HOST=localhost

### Chromecast

To use Chromecast, install [Castnow](https://github.com/xat/castnow) via `npm`:

    npm install castnow

Then set the name of your chromecast as an environment variable

	export CAST_DEVICE='Living_Room'   # Note, spaces in device names are not
	                                   # handled, rename your device via the
									   # mobile app.

`$CAST_DEVICE` will override `$MPD_HOST` and cause `radio` to playback via Chromecast.


I tend to set up bash aliases to configure my different locations, e.g.

    alias lr='export CAST_DEVICE=Living_Room; export MPD_HOST=rpi'
    alias l='unset CAST_DEVICE; unset MPD_HOST'   # local playback


### Digitally Imported

If you have a DI premium account, you can add a stream like this:

	di-ambient: http://listen.di.fm/premium/ambient.pls?listen_key=YOUR_DI_KEY

