#$L$
# Copyright (C) 2011 Ridgerun (http://www.ridgerun.com). 
##$L$

PKG_URL=http://procps.sourceforge.net/
PKG_TARBALL=procps-3.2.8.tar.gz
PKG_SHA1SUM=a0c86790569dec26b5d9037e8868ca907acc9829

BINARIES= /bin/{kill,ps}\
	 /sbin/sysctl\
	 /usr/bin/{free,pgrep,pkill,pmap,pwdx,skill,slabtop,snice,tload,top,uptime,vmstat,w,watch}
include ../../../bsp/classes/rrsdk.class
CFLAGS:=$(APPS_CFLAGS) -I$(FSDEVROOT)/usr/include/ncurses
LDFLAGS:=$(APPS_LDFLAGS)
DESTDIR?=$(FSDEVROOT)

FETCHER_EXTRACT_DIRECTORY_NAME=src

build: rrfetched built

built: rrpatched
	$(V) cd src && \
	$(MAKE) DESTDIR=$(DEVDIR)/fs/fs/ SHARED=0 $(TOOLCHAIN_ENVIRONMENT) LDFLAGS="$(LDFLAGS)" $(QOUT)

installed:
	$(V) cd src && \
	make install="install -D" SHARED=0 $(TOOLCHAIN_ENVIRONMENT) install DESTDIR=$(DESTDIR) $(QOUT)
	$(V) touch $@

install: installed rrsdk_install

uninstall:
	make install="install -D" uninstall $(QOUT)
	$(V) touch $@

clean: unpatch
	$(V) rm -Rf installed built

distclean: clean rrfetched_clean

include $(CLASSES)/fetcher.defs

