# Copyright (C) 2003, 2006, 2009 International Business Machines and others.
# All Rights Reserved.
# This file is distributed under the Common Public License.

## $Id$

AUTOMAKE_OPTIONS = foreign

EXTRA_DIST =

thirdpartylibdir = $(libdir)/coin/ThirdParty
thirdpartylib_LTLIBRARIES = libfiltersqp.la

libfiltersqp_la_SOURCES = \
	source/src/auxil.f \
	source/src/bqpd.f \
	source/src/filteraux.f \
	source/src/filter.f \
	source/src/QPsolves.f \
	source/src/scaling.f \
	source/src/sparseA.f \
	source/src/sparseL.f \
	source/src/util.f \
	source/src/wdotd.f

libfiltersqp_la_LDFLAGS = $(LT_LDFLAGS)

if COIN_HAS_PKGCONFIG
addlibsdir = $(datadir)/coin/doc/ThirdParty/FilterSQP
addlibs_DATA = filtersqp_addlibs.txt

filtersqp_addlibs.txt : coinfiltersqp.pc
	PKG_CONFIG_PATH=.:@COIN_PKG_CONFIG_PATH@ --libs coinfiltersqp > filtersqp_addlibs.txt
endif

pkgconfiglibdir = $(libdir)/pkgconfig
pkgconfiglib_DATA = coinfiltersqp.pc

########################################################################
#                         Maintainer Stuff                             #
########################################################################

CLEANFILES = filtersqp_addlibs.txt

# Files that are generated and should be cleaned with make distclean
DISTCLEANFILES =

include BuildTools/Makemain.inc
