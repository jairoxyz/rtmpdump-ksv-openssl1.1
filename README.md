# rtmpdump-ksv-openssl1.1+

These sources of rtmpdump from http://rtmpdump.mplayerhq.hu/ inlcude K-S-V patches from https://github.com/K-S-V/Scripts/releases and are updated to build and run with OpenSSL >= 1.1

To compile type "make" with SYS=<platform name>, e.g.

  $ make SYS=posix

for Linux, Unix, etc. (default)

To run against OpenSSL 1.1x to 3.5x set LD_LIBRARY_PATH to ./librtmp or use checkinstall to setup properly:

  $ make VERSION="v2.6-ksv\ 20251114.git138fdb2"
  
  $ sudo checkinstall --pakdir "$HOME/tmp" --pkgname librtmp-ksv --pkgversion "2.4-ksv+20251114.git138fdb2" --backup=no --default
  
  $ sudo ldconfig
  
On Ubuntu it otherwise uses the OS librtmp.so, which is compiled against GNUTLS.

To compile against GNUTLS:

  make CRYPTO=GNUTLS

More info and original sources can be found here: https://repo.or.cz/rtmpdump.git and here: http://git.ffmpeg.org/gitweb/rtmpdump.git and here: https://github.com/mirror/rtmpdump

Tested on Ubuntu 18+ only.

License: GPLv2
