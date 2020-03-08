# Audio::Libshout Examples

This directory contains examples of usage of Audio::Libshout, they all assume that you have a working Icecast server available


## [synopsis](synopsis)

This is the simplest working example,  it takes a single MP3 file as a command line argument and streams it to an Icecast on localhost
with the default configuration and a mount of `/foo`.

## [streamfile](streamfile)

This is a more complete example for streaming a single file which may be either MP3 or Ogg/Vorbis.  The host, port, mount, username can be
specified and the password and file are required.

```
Usage:
  examples/streamfile --password=<Str> --file=<Str> [--host=<Str>] [--port=<Int>] [--user=<Str>] [--mount=<Str>]
```

## [streamfile-encode](streamfile-encode)

This is a fuller example that will open any audio file recognized by `libsndfile`
encoding it to MP3 with [Audio::Encode::LameMP3](https://github.com/jonathanstowe/Audio-Encode-LameMP3) before streaming it.

The additional parameters are the bitrate and quality of the encoding.

Requires [Audio::Encode::LameMP3](https://github.com/jonathanstowe/Audio-Encode-LameMP3) and [Audio::Sndfile](https://github.com/jonathanstowe/Audio-Sndfile) to run, which can be installed with:

     zef install Audio::Encode::LameMP3 Audio::Sndfile

```
Usage:
  examples/streamfile-encode --password=<Str> --file=<Str> [--host=<Str>] [--port=<Int>] [--user=<Str>] [--bitrate=<Int>] [--quality=<Int>] [--bufsize=<Int>] [--mount=<Str>]
```
