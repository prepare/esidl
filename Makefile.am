if ENABLE_JAVA
JAVADIR = java
else
JAVADIR =
endif

SUBDIRS = . testsuite $(JAVADIR)
DIST_SUBDIRS = testsuite java

BUILT_SOURCES = lexer.cc parser.hh

bin_PROGRAMS = esidl

man1_MANS = esidl.1

esidl.1: esidl
	-$(HELP2MAN) -o $@ -n 'The Esidl Web IDL compiler' -N ./esidl

esidl_SOURCES = \
	include/cxx.h \
	include/esidl.h \
	include/expr.h \
	include/formatter.h \
	include/forward.h \
	include/info.h \
	include/java.h \
	include/messenger.h \
	include/messengerDispatch.h \
	include/messengerInvoke.h \
	include/messengerMeta.h \
	include/meta.h \
	include/reflect.h \
	include/sheet.h \
	include/utf.h \
	src/messenger.cpp \
	src/cxx.cpp \
	src/driver.cpp \
	src/esidl.cpp \
	src/java.cpp \
	src/help.cpp \
	src/lexer.ll \
	src/parser.yy \
	src/print.cpp \
	src/skeleton.cpp \
	src/template.cpp

esidl_CXXFLAGS = -D YYERROR_VERBOSE

clean-local:
	-rm -f $(BUILT_SOURCES) parser.cc parser.output $(nobase_nodist_include_HEADERS) esidl.1

dist-hook:
	-rm -f $(distdir)/lexer.cc $(distdir)/parser.cc $(distdir)/parser.hh

AM_YFLAGS = -d -v -t

AM_CPPFLAGS = \
	-iquote $(srcdir)/include \
	-iquote $(srcdir)/src

EXTRA_DIST = \
	install-prerequisites \
	esidl.spec.in \
	esidl.spec \
	debian/changelog \
	debian/changelog.in \
	debian/compat \
	debian/control \
	debian/copyright \
	debian/docs \
	debian/rules \
	debian/source/format \
	LICENSE \
	NOTICE \
	dom/COPYRIGHT.html \
	dom/2dcontext.idl \
	dom/arrays.idl \
	dom/console.idl \
	dom/cssom.idl \
	dom/cssomview.idl \
	dom/dom2css.idl \
	dom/dom2events.idl \
	dom/dom2ranges.idl \
	dom/dom2stylesheets.idl \
	dom/dom2traversal.idl \
	dom/dom2views.idl \
	dom/dom3core.idl \
	dom/dom3events.idl \
	dom/dom3ls.idl \
	dom/dom3validation.idl \
	dom/dom3xpath.idl \
	dom/domcore.idl \
	dom/elementtraversal.idl \
	dom/eventsource.idl \
	dom/file.idl \
	dom/geolocation.idl \
	dom/html5.idl \
	dom/idl_scraper.pl \
	dom/indexeddb.idl \
	dom/microdata.idl \
	dom/NOTICE \
	dom/postmsg.idl \
	dom/progress-events.idl \
	dom/selectors.idl \
	dom/smil.idl \
	dom/svg.idl \
	dom/typedarray.idl \
	dom/url.idl \
	dom/webdatabase.idl \
	dom/webgl.idl \
	dom/webnotifications.idl \
	dom/webstorage.idl \
	dom/websocket.idl \
	dom/wget_webidl_dom \
	dom/workers.idl \
	dom/xhr2.idl \
	setup.pepper
