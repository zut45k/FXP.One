FXP.One
=======

First of all many thanks to lundman for a great ftp/fxp engine!!!

To compile/install/use please read lundman's documentation on his website.

If you want to use the engine with ftps implicit/explicit SSL/TLS you probably need to modify the cfg_tlsciphers in tls.c in the lion library to: static char cfg_tlsciphers[] = "ALL";

linknet/#fxp.one

CHANGES:

2017-12-23: first attempt on adding 'stat -al' support for fxp.one... still learning the code and github so don't shoot me ;-)
The engine was modified to support 'stat -al' dirlisting and use_stat with yna-type in the sitedefinition to make stat/list configurable. Therefore also the API was changed, SITELIST now includes USE_STAT in it's reply e.g.:

      SITELIST|SITEID=1|NAME=localhost2|HOST=127.0.0.1|PORT=56688|USER=test|PASS=ing|USE_STAT=2|PASSIVE=1|
            FXP_PASSIVE=2|CONTROL_TLS=2|DATA_TLS=2


--------------------------------------------------------------------------------------------------------------------------------------
below follows the original README.md from lundman.

http://lundman.net/wiki/index.php/FXP.One

FXP.One is a whole new system to FTP and FXP. It is not just another
FTP client. It is in fact a very flexible FTP/FXP engine.

This engine does all the hard work with dealing with FTP sites. Built
into that is a very simple but powerful API protocol.

The idea is then, if someone wants to do an FTP, or FXP, client they
can then make one without the FTP hassles.

Currently there already are multiple clients. They all talk to the
FXP.One engine, and you can interchange the clients.

That is, use one client to create and queue up some items and start
the queue process. At a later time, a different client, from a
different machine/location can connect and check on the progress of
that queue, change it, modify and add to it and so on.

The FXP.One engine features:
* Full FTP and FXP capabilities.
* SSL/TLS support, auto-sensing and forced.
* SSL/TLS data support, auto-sensing and forced.
* SSCN secure data FXP support.
* CCSN secure data FXP support.
* XDUPE aware for faster queue processing.
* Auto resume, or overwrite options
* Resume last (re-queue all resume items last for faster queue processing)
* FXP direction control (if one site is firewalled)
* PRET Pre-transfer support for ring-sites.
* Skip lists for both files and directories
* Pass lists for both files and directories (opposite to skip list)
* Move-first for both files and directories
* Automatic skip of empty files and directories.
* Encodes all file and directory names as to handle any locale.

FXP.One aims to be as portable as possible. It currently runs on all
flavours of Unix, OSX and Windows.

Clients that ship with FXP.One are;

* WFXP
  A browser, WebSockets, FXP client. Works in most modern browsers,
  like Chrome and Firefox. (Notably, does not work in Safari-2012).

* Clomps
  command-line (no GUI) client that connects to multiple servers, and
  displays all new directories and files since last run. Great for
  finding what is new, and where it is. (and where it isn't).
  Clomps can also automatically create queues to keep FTP servers
  synchronised. Ie, auto-trading.

* Clomps-irc
  Auto-trader for IRC bots.

* FXP.cOne
  Early ncurses FXP client.

There are also a number of external clients which use FXP.One, for
example,

* UFXP
  Ultimate-++ toolkid FXP client. The WFXP client seeks to replace
  this work.

FXP.One has very simple API for developers, you can very easily FTP
and FXP using just telnet, if you so wanted. This means clients in
perl, python and similar languages are really easy to implement.

Please more about the API in the documentation;

http://lundman.net/wiki/index.php/Protocol




