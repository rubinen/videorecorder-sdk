#$L$
# Copyright (C) 2011 Ridgerun (http://www.ridgerun.com). 
##$L$

PKG_URL=http://www.mr511.de/software/
PKG_TARBALL=libelf-0.8.13.tar.gz
PKG_SHA1SUM=c1d6ac5f182d19dd685c4dfd74eedbfe3992425d

export ac_cv_sizeof_long_long=8
export ac_cv_sizeof_long_long+set=set
AUTOTOOLS_PARAMS= --enable-shared --disable-sanity-checks  --enable-elf64

export libelf_cv_working_memmove=yes
export mr_cv_target_elf=yes

LIBRARIES=/usr/lib/libelf.so.0.8.13

include ../../../bsp/classes/rrsdk.class
include $(CLASSES)/autotools.class

