#$L$
# Copyright (C) 2011 Ridgerun (http://www.ridgerun.com). 
##$L$

PKG_URL=http://sourceforge.net/projects/oprofile/files/oprofile/oprofile-0.9.6/
PKG_TARBALL=oprofile-0.9.6.tar.gz
PKG_SHA1SUM=cc62cc58c574e235bc146c8ddc9d9a9af0972fd1

include ../../../bsp/classes/rrsdk.defs
# Workaround for faulty toolchain
CPPFLAGS+=-I$(subst ",,$(CONFIG_TOOLCHAIN_PATH))/arm-linux-gnueabi/usr/include/c++/ -I$(subst ",,$(CONFIG_TOOLCHAIN_PATH))/arm-linux-gnueabi/usr/include/c++/arm-linux-gnueabi -I$(FSDEVROOT)/usr/include
export LDFLAGS:=$(APPS_LDFLAGS) -Wl,--rpath-link -Wl,$(FSDEVROOT)/usr/lib
AUTOTOOLS_PARAMS=--with-kernel-support

BINARIES = /usr/bin/{ophelp,opcontrol,oparchive,oprofiled,opreport}

include $(CLASSES)/autotools.class

