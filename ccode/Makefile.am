include $(top_srcdir)/Makefile.common

NULL =

AM_CPPFLAGS = \
	$(COVERAGE_CFLAGS) \
	-I$(top_builddir)/gee \
	$(GLIB_CFLAGS) \
	$(NULL)

BUILT_SOURCES = ccode.vala.stamp

noinst_LTLIBRARIES = \
	libvalaccode.la \
	$(NULL)

libvalaccode_la_VALASOURCES = \
	valaccodeassignment.vala \
	valaccodebinaryexpression.vala \
	valaccodeblock.vala \
	valaccodebreakstatement.vala \
	valaccodecasestatement.vala \
	valaccodecastexpression.vala \
	valaccodecommaexpression.vala \
	valaccodecomment.vala \
	valaccodeconditionalexpression.vala \
	valaccodeconstant.vala \
	valaccodecontinuestatement.vala \
	valaccodedeclaration.vala \
	valaccodedeclarator.vala \
	valaccodedostatement.vala \
	valaccodeemptystatement.vala \
	valaccodeenum.vala \
	valaccodeenumvalue.vala \
	valaccodeexpression.vala \
	valaccodeexpressionstatement.vala \
	valaccodefile.vala \
	valaccodeforstatement.vala \
	valaccodefragment.vala \
	valaccodefunction.vala \
	valaccodefunctioncall.vala \
	valaccodefunctiondeclarator.vala \
	valaccodeggnucsection.vala \
	valaccodegotostatement.vala \
	valaccodeidentifier.vala \
	valaccodeifstatement.vala \
	valaccodeincludedirective.vala \
	valaccodeinitializerlist.vala \
	valaccodeinvalidexpression.vala \
	valaccodelabel.vala \
	valaccodelinedirective.vala \
	valaccodeifsection.vala \
	valaccodemacroreplacement.vala \
	valaccodememberaccess.vala \
	valaccodemodifiers.vala \
	valaccodenewline.vala \
	valaccodenode.vala \
	valaccodeoncesection.vala \
	valaccodeparameter.vala \
	valaccodeparenthesizedexpression.vala \
	valaccodereturnstatement.vala \
	valaccodestatement.vala \
	valaccodestruct.vala \
	valaccodeswitchstatement.vala \
	valaccodetypedefinition.vala \
	valaccodeunaryexpression.vala \
	valaccodevariabledeclarator.vala \
	valaccodewhilestatement.vala \
	valaccodewriter.vala \
	valaccodeelementaccess.vala \
	$(NULL)

libvalaccode_la_SOURCES = \
	ccode.vala.stamp \
	$(libvalaccode_la_VALASOURCES:.vala=.c) \
	$(NULL)

ccodeincludedir = $(includedir)/vala@PACKAGE_SUFFIX@

ccodeinclude_HEADERS = \
	valaccode.h \
	$(NULL)

ccode.vapi ccode.vala.stamp: $(libvalaccode_la_VALASOURCES)
	$(VALA_V)$(VALAC) \
		$(COVERAGE_VALAFLAGS) \
		$(VALAFLAGS) \
		-C \
		--vapidir $(top_srcdir)/vapi --pkg gobject-2.0 \
		--vapidir $(top_builddir)/gee --pkg gee \
		--pkg config \
		-H valaccode.h \
		--library ccode \
		$^
	touch $@

libvalaccode_la_LIBADD = \
	$(COVERAGE_LIBS) \
	$(GLIB_LIBS) \
	$(NULL)

EXTRA_DIST = $(libvalaccode_la_VALASOURCES) ccode.vapi ccode.vala.stamp

MAINTAINERCLEANFILES = \
	ccode.vapi \
	valaccode.h \
	$(libvalaccode_la_VALASOURCES:.vala=.c) \
	$(NULL)
