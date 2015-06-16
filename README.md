np1sec
======

[![Build Status](https://travis-ci.org/equalitie/np1sec.svg?branch=master)](https://travis-ci.org/equalitie/np1sec)

Multiparty communication security implementation of the protocol described by this [paper](https://learn.equalit.ie/wiki/Np1sec)

![(n+1)sec](https://learn.equalit.ie/mw/images/7/7f/Np1sec-web.jpg)

Debug
----
To debug with gdb

libtool --mode=execute gdb -i=mi xmpp_test

# Installaton
     
The following instructions describe the steps required to build np1sec from scratch on a freshly installed system running debian 8.1 stable.  It is assumed that software such as `git` and `build-essential` are already present.
     
Commands prefixed with `#` are to be run as root or a super user.
Those prefixed with `$` can (should) be run as an unprivileged user.
     
## autoconf
 
```
$ wget http://ftp.gnu.org/gnu/autoconf/autoconf-2.69.tar.gz
$ tar -xzf autoconf-2.69.tar.gz
$ cd autoconf-2.69
$ ./configure
$ make
# make install
$ cd ..
```
 
## automake
 
```
$ wget http://ftp.gnu.org/gnu/automake/automake-1.15.tar.gz
$ tar -xzf automake-1.15.tar.gz
$ cd automake-1.15
$ ./configure
$ make
# make install
$ cd ..
```
 
## libtool
 
```
$ wget http://gnu.mirror.iweb.com/libtool/libtool-2.4.6.tar.gz
$ tar -xzf libtool-2.4.6.tar.gz
$ cd libtool-2.4.6
$ ./configure
$ make
# make install
$ cd ..
```
 
## libgpg-error
 
```
# apt-get install gettext
$ wget ftp://ftp.gnupg.org/gcrypt/libgpg-error/libgpg-error-1.19.tar.bz2
$ tar -xvf libgpg-error-1.19.tar.bz2
$ cd libgpg-error-1.19
$ ./autogen.sh
$ ./configure
$ make
# make install
$ cd ..
```
 
## libgcrypt
 
```
# apt-get install libpurple0 libpurple-dev
# apt-get install libglib2.0-0 libglib2.0-dev
# apt-get install libevent-2.0-5 libevent-dev
# apt-get install xfig
$ git clone -b vmon-eddh https://github.com/equalitie/libgcrypt.git
$ cd libgcrypt
$ ./autogen.sh
$ ./configure --enable-maintainer-mode
$ make
# make install
$ cd ..
```
 
## haveged
 
Haveged is used to generate entropy more quickly.  You may or may not want it.
 
```
# apt-get install haveged
```
 
## np1sec
 
```
$ wget https://learn.equalit.ie/mw/images/a/a0/Np1sec.tar.gz.zip
$ unzip np1sec.tar.gz.zip
$ tar -xzf np1sec.tar.gz
$ cd np1sec
$ ./configure
$ make
```
 
### Run the tests
 
```
$ ./libnp1sec_test
```
