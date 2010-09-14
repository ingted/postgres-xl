#-------------------------------------------------------------------------
#
# Makefile for src/gtm
# GTM and GTM proxy
#
# Copyright (c) 2010 Nippon Telegraph and Telephone Corporation
#-------------------------------------------------------------------------

PGFILEDESC = "gtm - Global Transaction Manager for Postgres-XC"
subdir = src/gtm
top_builddir = ../..
include $(top_builddir)/src/Makefile.global

WANTED_DIRS=common path libpq client main proxy gtm_ctl

all:
	@for dir in $(WANTED_DIRS); do \
        $(MAKE) -C $$dir $@ || exit; \
    done

clobber:
	@for dir in $(WANTED_DIRS); do \
        $(MAKE) -C $$dir $@ || exit; \
    done

clean:
	@for dir in $(WANTED_DIRS); do \
        $(MAKE) -C $$dir $@ || exit; \
    done

distclean: clean

maintainer-clean: distclean

install: all 
	$(INSTALL_PROGRAM) ./main/gtm$(X) '$(DESTDIR)$(bindir)/gtm$(X)'
	$(INSTALL_PROGRAM) ./gtm_ctl/gtm_ctl$(X) '$(DESTDIR)$(bindir)/gtm_ctl$(X)'
	$(INSTALL_PROGRAM) ./proxy/gtm_proxy$(X) '$(DESTDIR)$(bindir)/gtm_proxy$(X)'

uninstall:
	rm -f $(DESTDIR)$(bindir)/gtm$(X)
	rm -f $(DESTDIR)$(bindir)/gtm_ctl$(X)
	rm -f $(DESTDIR)$(bindir)/gtm_proxy$(X)