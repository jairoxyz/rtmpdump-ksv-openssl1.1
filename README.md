# rtmpdump-ksv-openssl1.1

These sources of rtmpdump from http://rtmpdump.mplayerhq.hu/ inlcude K-S-V patches from https://github.com/K-S-V/Scripts/releases and are updated to build and run with OpenSSL 1.1x (patches based on https://github.com/xbmc/inputstream.rtmp/tree/master/depends/common/librtmp)

To compile type "make" with SYS=<platform name>, e.g.

  $ make SYS=posix

for Linux, Unix, etc. (default)

To run against OpenSSL 1.1x set LD_LIBRARY_PATH to ./librtmp or use checkinstall to setup properly:

  $ make VERSION="v2.4-ksv\ 20151223.gitfa8646d"
  
  $ sudo checkinstall --pakdir "$HOME/tmp" --pkgname librtmp-ksv --pkgversion "2.4-ksv+20151223.gitfa8646d" --backup=no --default
  
  $ sudo ldconfig
  
On Ubuntu it otherwise uses the OS librtmp.so, which is compiled against GNUTLS.

To compile against GNUTLS:

  $ make CRYPTO=GNUTLS

You may also build with just rtmpe support, and no rtmps/https support, by
specifying -DNO_SSL in the XDEF macro, e.g.

  $ make XDEF=-DNO_SSL

or

  $ make CRYPTO=POLARSSL XDEF=-DNO_SSL

You may also turn off all crypto support if desired

  $ make CRYPTO=

A shared library is now built by default, in addition to the static
library. You can also turn it off if desired

  $ make SHARED=

The rtmpdump programs still link to the static library, regardless.

More info and original sources can be found here: https://repo.or.cz/rtmpdump.git and here: http://git.ffmpeg.org/gitweb/rtmpdump.git and here: https://github.com/mirror/rtmpdump

Tested on Ubuntu 16/18 only.

License: GPLv2
