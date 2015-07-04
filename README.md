# Audio::Libshout

Perl 6 binding to libshout - provide icecast/streaming client

## Description

This provides a source client to stream to an icecast server.  It can stream Ogg/Vorbis or MP3
data but doesn't provide any transcoding so the data will need to be provided from an appropriate
source in the required encoding. This has been developed against version 2.2.2 of libshout, it is
possible later versions may provide support for other encodings.

The API is somewhat simplified in comparison to libshout but provides an asynchronous mechanism
whereby data can be fed as quickly as it is obtained to a worker thread via a channel so the client
doesn't have to worry about the timing and synchronisation issues, though the lower level send and
sync methods are available if your application requires a different scheme.

In testing this proved quite capable of streaming a 320kb/s MP3 read from a file to an icecast
server on the local network, though of course network conditions may limit the rate that will work
well to remote servers.

If you're curious the first thing that I streamed using this library was

https://www.mixcloud.com/mikestern-awakening/mike-stern-guest-mix-for-technotic-eire-radio-show/

Mike's a great DJ, great DJs and producers make making software worthwhile :)

## Installation

You will need to have "libshout"  installed on your system in order to
be able to use this. Most Linux distributions offer it as a package.


If you are on some platform that doesn't provide libshout as a package
then you may be able to install it from source:

https://github.com/xiph/Icecast-libshout

I am however unlikely to be able to offer help with installing it this way, also bear in mind that
if you install a newer version than I have to test with then this may not work.

Assuming you have a working perl6 installation you should be able to
install this with *ufo* :

    ufo
    make test
    make install

*ufo* can be installed with *panda* for rakudo:

    panda install ufo

Or you can install directly with "panda":

    # From the source directory
   
    panda install .

    # Remote installation

    panda install Audio::Libshout

Other install mechanisms may be become available in the future.

## Support

This should be considered experimental software until such time that
Perl 6 reaches an official release.  However suggestions/patches are
welcomed via github at

https://github.com/jonathanstowe/Audio-Libshout

I have tested this and found it to work with my installation of icecast,
so it should work anywhere else, if however you experience a problem
with streaming please test with another source client such as ices or darkice
before reporting a bug as I am unlikely to be able to help you with your
streaming configuration.

## Licence

Please see the LICENCE file in the distribution

(C) Jonathan Stowe 2015
