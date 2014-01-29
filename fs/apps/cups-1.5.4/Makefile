#$L$
# Copyright (C) 2011 Ridgerun (http://www.ridgerun.com)
##$L$

PKG_URL=http://www.cups.org/software/1.5.4
PKG_TARBALL=cups-1.5.4-source.tar.gz
PKG_SHA1SUM=4e3281e02b412b379e6f6ebd868f6ad4b2367f60

ADD_GROUPS=lp:x:7:
ADD_USERS_TO_GROUPS=root:lp

BINARIES= /usr/bin/{cancel,cups-config,lp,lpq,lpr,lprm,lpstat,ppdi,ppdmerge,ppdpo,ppdhtml,lpoptions,lppasswd}\
/usr/sbin/{accept,cupsaccept,cupsctl,cupsd,cupsdisable,cupsenable,cupsfilter,cupsreject,lpadmin,lpc,lpinfo,lpmove,reject}
LIBRARIES = /usr/lib/{libcupscgi.so.1,libcupsdriver.so.1,libcupsimage.so.2,libcupsmime.so.1,libcupsppdc.so.1,libcups.so.2}
EXTRA_FILES = /usr/share/cups/{banners,charsets,data,drv,fonts,mime,model,profiles} /etc/cups \
/var/{cache/cups,run/cups,log/cups,spool/cups} /usr/lib/cups

INIT_SCRIPT=cupsd.init
INIT_SCRIPT_DEPENDENCIES=mountall

export LDFLAGS =-Wl,--rpath-link -Wl,$(FSDEVROOT)/usr/lib -L$(FSDEVROOT)/usr/lib
export DSOFLAGS=-L$(FSDEVROOT)/usr/lib
export DSTROOT=$(FSDEVROOT)

# Cups does not build fine outside itself
AUTOTOOLS_CLONE_SOURCE=yes
AUTOTOOLS_PARAMS=--disable-gssapi --disable-ssl --with-cups-system-groups=pl --without-php --enable-libusb\
--disable-dbus --prefix=/usr --sysconfdir=/etc --localstatedir=/var

default_target: build

.PHONY: install autotools_installed


# Before installing the extra_files we need to erase the current files
# which have different permissions and could cause conflicts
install::
	echo "HACK: Removing all cups software before rebuilding to get around tar error"; 
	$(V)for extra_file in $(EXTRA_FILES) ; do \
	    $(SUDO) rm -rf $(FSROOT)/$$extra_file ; \
	done

include ../../../bsp/classes/rrsdk.class
include $(CLASSES)/autotools.class

# Correct cups-config, and some file permissions
install:: 
	$(V)sed -i -e 's?prefix=/usr?prefix=$(FSDEVROOT)/usr?' \
	           -e 's?dir=/usr?dir=$(FSDEVROOT)/usr?' \
	                $(FSDEVROOT)/usr/bin/cups-config
	$(V) cp $(FSDEVROOT)/usr/bin/cups-config $(LOCALDIR)/bin
	$(V) if test -d $(FSROOT)/usr/lib/cups/ ; then  $(SUDO) chown -R --from=root:lp `id -nu`:`id -ng` $(FSROOT)/usr/lib/cups/  ; fi
	$(V) $(SUDO) chmod 777 $(LOCALDIR)/bin/cups-config
	$(V) $(SUDO) chmod 666 $(FSDEVROOT)/usr/share/cups/mime/mime.{convs,types}

clean::
	$(V) $(SUDO) rm -rf $(FSROOT)/usr/lib/cups/ $(FSROOT)/etc/cups $(FSDEVROOT)/usr/share/cups
