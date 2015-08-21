spotifyripper
=============

Rips music from Spotify as it plays through the Spotify Linux client on Debian/Ubuntu

**Using this script propably violates [Spotifys](https://spotify.com) [User Agreement](https://www.spotify.com/legal/end-user-agreement/)**

Run with:
```bash
./ripper.sh your_music_directory
```

If no directory is specified, it dumps into the current directory.
Requires that Spotify is running and has played music *before* the ripper is ran and no other music software is running.

This application records the audio that is played from Spotify, much like one would rip songs from a radio.

## Features

The recorded audio is automatically splitted and tagged with the artist, song name, track number, and album cover image information, and encoded in 192kbps ogg vorbis.

Because audio interruptions can occur which get recorded along with the song, the ripper gains control over the sound output so only the sound coming from Spotify gets recorded, meaning Spotify will ~~not~~ play through the speakers, however no other sound playing on the machine will be recorded during the rip.

[skimmilk](https://github.com/skimmilk)'s [script](https://github.com/skimmilk/spotifyripper) redirected spotify's sound output to a null-sink which then got recorded. Because I want to listen to the music while it gets recorded I created this fork which instead creates a combine-sink. If you change the volume, pause the music or output other stuff to the combine-sink during the recording it will be in the resulting ogg file.

In order to control and rip Spotify's audio, the client has to be registered with the audio server, which only happens when Spotify plays a sound or song.

**ATTENTION:** I haven't tested this much. Just forked the original cause i wanted to rip and listen :D
