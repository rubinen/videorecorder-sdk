#$L$
# Copyright (C) 2012 Ridgerun (http://www.ridgerun.com).
##$L$

PKG_URL=http://lttng.org/files/lttng-tools/
PKG_TARBALL=lttng-tools-2.0.0-rc1.tar.bz2
PKG_SHA1SUM=1424b8b6b261350c3fc8aa74ab9b9603ddc6b11f

LDFLAGS=-L$(FSDEVROOT)/usr/lib -Wl,--rpath -Wl,$(FSDEVROOT)/usr/lib 

# Lttng can't do an out-of-tree build
AUTOTOOLS_CLONE_SOURCE=yes
AUTOTOOLS_PARAMS=LDFLAGS="$(LDFLAGS)" --prefix=/usr
DESTDIR=$(FSDEVROOT)

include ../../../bsp/classes/rrsdk.class

BINARIES = /usr/bin/{lttng,lttng-consumerd,lttng-sessiond}
LIBRARIES = /usr/lib/liblttng-ctl.so.0.0.0

CORRECT_LA = /usr/lib/liblttng-ctl.la

include $(CLASSES)/autotools.class

