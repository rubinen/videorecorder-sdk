#$L$
# Copyright (C) 2013 Ridgerun (http://www.ridgerun.com). 
##$L$

PKG_URL=http://downloads.sourceforge.net/rpcbind
PKG_TARBALL=rpcbind-0.2.1.tar.bz2
PKG_SHA1SUM=d1ca8ce155d98d4f1c1dd40fa747a2144a42cb61

AUTOTOOLS_PARAMS= --with-rpcuser=root
BINARIES = /usr/bin/{rpcbind,rpcinfo}
INIT_SCRIPT=rpcbind.init
INIT_SCRIPT_LEVEL=90

include ../../../bsp/classes/rrsdk.defs
include $(CLASSES)/autotools.class
