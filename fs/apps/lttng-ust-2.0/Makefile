#$L$
# Copyright (C) 2012 Ridgerun (http://www.ridgerun.com).
##$L$

PKG_URL=http://lttng.org/files/lttng-ust/
PKG_TARBALL=lttng-ust-2.0.0-rc1.tar.gz
PKG_SHA1SUM=6f63957328f4ba7df9311a24300a0bacae5899db

include ../../../bsp/classes/rrsdk.class

BINARIES = /usr/bin/lttng-gen-tp
LIBRARIES = /usr/lib/{liblttng-ust-ctl.so.0.0.0,liblttng-ust-fork.so.0.0.0,liblttng-ust-libc-wrapper.so.0.0.0,liblttng-ust-tracepoint.so.0.0.0,liblttng-ust.so.0.0.0}

include $(CLASSES)/autotools.class

