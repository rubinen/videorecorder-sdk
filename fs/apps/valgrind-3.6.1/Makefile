#$L$
# Copyright (C) 2011 Ridgerun (http://www.ridgerun.com). 
##$L$

PKG_URL=http://valgrind.org/downloads/
PKG_TARBALL=valgrind-3.6.1.tar.bz2
PKG_SHA1SUM=6116ddca2708f56e0a2851bdfbe88e01906fa300

DESTDIR=$(FSDEVROOT)
AUTOTOOLS_HOST=--host=armv7-none-linux-gnueabi
AUTOTOOLS_PARAMS=--prefix=/usr
AUTOTOOLS_CLONE_SOURCE=yes
AUTOTOOLS_AUTOGEN_PARAMS=--noconfigure

BINARIES= usr/bin/{callgrind_annotate,callgrind_control,cg_annotate,cg_diff,cg_merge,ms_print,no_op_client_for_valgrind,valgrind,valgrind-listener}
LIBRARIES= usr/lib/valgrind/{cachegrind-arm-linux,callgrind-arm-linux,drd-arm-linux,exp-bbv-arm-linux,exp-dhat-arm-linux} \
	usr/lib/valgrind/{exp-ptrcheck-arm-linux,helgrind-arm-linux,lackey-arm-linux,massif-arm-linux,memcheck-arm-linux,none-arm-linux} \
	usr/lib/valgrind/{vgpreload_core-arm-linux.so,vgpreload_drd-arm-linux.so,vgpreload_exp-dhat-arm-linux.so,vgpreload_massif-arm-linux.so} \
	usr/lib/valgrind/{vgpreload_helgrind-arm-linux.so,vgpreload_exp-ptrcheck-arm-linux.so,vgpreload_memcheck-arm-linux.so}

include ../../../bsp/classes/rrsdk.class

export KERNEL

ifeq ($(MAKECMDGOALS),build)
 ifneq ($(CONFIG_CPU_V7),yes)
   $(error Valgrind is only supported on processors of ARM familiy V7 and up. Please disable valgrind to continue building)
 endif
endif

include $(CLASSES)/autotools.class

