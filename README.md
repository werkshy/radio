# RADIO

## Overview
Radio is a small command line wrapper around mpc for listening to internet
radio streams with [MPD](http://www.musicpd.org/)

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

### Digitally Imported

If you have a DI premium account, you can add a stream like this:

	di-ambient: http://listen.di.fm/premium/ambient.pls?listen_key=YOUR_DI_KEY

