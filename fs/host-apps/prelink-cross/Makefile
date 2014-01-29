#$L$
# Copyright (C) 2011 Ridgerun (http://www.ridgerun.com). 
##$L$

PKG_URL=git://git.pokylinux.org/prelink-cross
PKG_REVISION=f51f4a5db605ab542ab06334fcad1d5bdba91048
AUTOTOOLS_SRC_DIR=src/trunk
AUTOTOOLS_PARAMS=CPPFLAGS="-I$(LOCALDIR)/include -I$(LOCALDIR)/include/libelf" LDFLAGS="-L$(LOCALDIR)/lib" --enable-static
AUTOTOOLS_CLONE_SOURCE=yes

include ../../../bsp/classes/rrsdk.class

AUTOTOOOLS_AUTOGEN_GENERATION_RULE=$(AUTOTOOLS_SRC_DIR)/autogen.sh

$(AUTOTOOLS_SRC_DIR)/autogen.sh:
	$(V)cd $(AUTOTOOLS_SRC_DIR) ; \
	 libtoolize --copy --force $(QOUT) $(ERRQOUT) ; \
	 aclocal -I m4 $(QOUT) $(ERRQOUT) ; \
	 autoconf $(QOUT) $(ERRQOUT) ; \
	 automake --add-missing $(QOUT) $(ERRQOUT)
	$(V) touch $@
	$(V) chmod +x $@

include $(CLASSES)/autotools_local.class

install::
	$(V) if [ ! -f $(LOCALDIR)/sbin/prelink.orig ] ; then \
	  mv $(LOCALDIR)/sbin/prelink $(LOCALDIR)/sbin/prelink.orig ; \
	  sed -e "s?@DEVDIR@?$(DEVDIR)?" prelink.in > $(LOCALDIR)/sbin/prelink ;\
	  chmod +x $(LOCALDIR)/sbin/prelink ;\
	fi
	$(V) if [ ! -f $(LOCALDIR)/sbin/prelink-rtld.orig ] ; then \
	  mv $(LOCALDIR)/sbin/prelink-rtld $(LOCALDIR)/sbin/prelink-rtld.orig ; \
	  sed -e "s?@DEVDIR@?$(DEVDIR)?" prelink.in > $(LOCALDIR)/sbin/prelink-rtld ;\
	  chmod +x $(LOCALDIR)/sbin/prelink-rtld ;\
	fi
