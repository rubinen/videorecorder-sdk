#$L$
# Copyright (C) 2013 Ridgerun (http://www.ridgerun.com).
##$L$

PKG_URL=http://downloads.sourceforge.net/nfs
PKG_TARBALL=nfs-utils-1.2.9.tar.bz2
PKG_SHA1SUM=16b277a36375e78a367dab5dd7599c2f4a7eb933

DESTDIR=$(FSDEVROOT)
AUTOTOOLS_BUILD_DIR=src
AUTOTOOLS_PARAMS= --without-tcp-wrappers --disable-nfsv4 --disable-gss --disable-uuid --prefix=/usr

BINARIES =  /sbin/{mount.nfs,mount.nfs4,osd_login,umount.nfs,umount.nfs4} \
	    /usr/sbin/{exportfs,mountstats,nfsiostat,nfsstat,rpcdebug,rpc.mountd} \
	    /usr/sbin/{rpc.nfsd,rpc.statd,showmount,sm-notify,start-statd}
EXTRA_FILES = /var/lib/nfs
INIT_SCRIPT=nfs-server.init
INIT_SCRIPT_LEVEL=99

include ../../../bsp/classes/rrsdk.defs
include $(CLASSES)/autotools.class
