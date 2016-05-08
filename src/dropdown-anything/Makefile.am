## Process this file with automake to produce Makefile.in
PFLAGS=-module -avoid-version -no-undefined

libddanything_la_LDFLAGS = $(PFLAGS)
libddanything_la_LIBADD = @COMPIZ_LIBS@
nodist_libddanything_la_SOURCES = ddanything_options.c ddanything_options.h
dist_libddanything_la_SOURCES = ddanything.c

BUILT_SOURCES = $(nodist_libddanything_la_SOURCES)

AM_CPPFLAGS =                              \
	-I$(top_srcdir)/include             \
	@COMPIZ_CFLAGS@                     \
	-DDATADIR='"$(compdatadir)"'        \
	-DLIBDIR='"$(libdir)"'              \
	-DLOCALEDIR="\"@datadir@/locale\""  \
	-DIMAGEDIR='"$(imagedir)"'

moduledir = $(plugindir)

module_LTLIBRARIES = libddanything.la

CLEANFILES = *_options.c *_options.h

ddanything_options.h: ../../metadata/ddanything.xml.in
		$(BCOP_BIN) --header $@ $<

ddanything_options.c: ../../metadata/ddanything.xml.in ddanything_options.h
		$(BCOP_BIN) --source $@ $<
