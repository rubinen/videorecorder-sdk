#$L$
# Copyright (C) 2011 Ridgerun (http://www.ridgerun.com).
##$L$

PKG_URL=http://lttng.org/files/urcu/
PKG_TARBALL=userspace-rcu-0.6.7.tar.bz2
PKG_SHA1SUM=ff77001c7063c40e28a65840584740803b34730b

LIBRARIES = /usr/lib/{liburcu-bp.so.1.0.0,liburcu-cds.so.1.0.0,liburcu-mb.so.1.0.0,liburcu-qsbr.so.1.0.0,liburcu-signal.so.1.0.0,liburcu.so.1.0.0,liburcu-common.so.1.0.0}

AUTOTOOLS_CLONE_SOURCE=yes
AUTOTOOLS_PARAMS=ac_cv_func_malloc_0_nonnull=yes

include ../../../bsp/classes/rrsdk.class
include $(CLASSES)/autotools.class

