
SHELL = /bin/sh

#### Start of system configuration section. ####

srcdir = .
topdir = /usr/lib/ruby/1.8/i686-linux
hdrdir = $(topdir)
VPATH = $(srcdir):$(topdir):$(hdrdir)
prefix = $(DESTDIR)/usr
exec_prefix = $(prefix)
libdir = $(exec_prefix)/lib
vendorlibdir = $(vendordir)/$(ruby_version)
sitelibdir = $(sitedir)/$(ruby_version)
oldincludedir = $(DESTDIR)/usr/include
vendorarchdir = $(vendorlibdir)/$(sitearch)
sitearchdir = $(sitelibdir)/$(sitearch)
bindir = $(exec_prefix)/bin
sharedstatedir = $(prefix)/com
docdir = $(datarootdir)/doc/$(PACKAGE)
localstatedir = $(DESTDIR)/var
dvidir = $(docdir)
archdir = $(rubylibdir)/$(arch)
vendordir = $(libdir)/ruby/vendor_ruby
htmldir = $(docdir)
pdfdir = $(docdir)
psdir = $(docdir)
libexecdir = $(prefix)/lib/ruby1.8
localedir = $(datarootdir)/locale
sysconfdir = $(DESTDIR)/etc
mandir = $(prefix)/share/man
datarootdir = $(prefix)/share
sbindir = $(exec_prefix)/sbin
rubylibdir = $(libdir)/ruby/$(ruby_version)
includedir = $(prefix)/include
sitedir = $(DESTDIR)/usr/local/lib/site_ruby
infodir = $(prefix)/share/info
datadir = $(datarootdir)

CC = gcc
LIBRUBY = $(LIBRUBY_SO)
LIBRUBY_A = lib$(RUBY_SO_NAME)-static.a
LIBRUBYARG_SHARED = -l$(RUBY_SO_NAME)
LIBRUBYARG_STATIC = -l$(RUBY_SO_NAME)-static

RUBY_EXTCONF_H = 
CFLAGS   =  -fPIC -fno-strict-aliasing -g -g -O2  -fPIC $(cflags) 
INCFLAGS = -I. -I. -I/usr/lib/ruby/1.8/i686-linux -I.
DEFS     = -D_FILE_OFFSET_BITS=64
CPPFLAGS = -DHAVE_SQLITE3_INITIALIZE -DHAVE_SQLITE3_BACKUP_INIT -DHAVE_SQLITE3_COLUMN_DATABASE_NAME -DHAVE_SQLITE3_ENABLE_LOAD_EXTENSION -DHAVE_SQLITE3_LOAD_EXTENSION -D_FORTIFY_SOURCE=2 -D_FILE_OFFSET_BITS=64 -D_FORTIFY_SOURCE=2
CXXFLAGS = $(CFLAGS) 
ldflags  = -L. -Wl,-Bsymbolic-functions -Wl,-z,relro -rdynamic -Wl,-export-dynamic
dldflags = 
archflag = 
DLDFLAGS = $(ldflags) $(dldflags) $(archflag)
LDSHARED = $(CC) -shared
AR = ar
EXEEXT = 

RUBY_INSTALL_NAME = ruby1.8
RUBY_SO_NAME = ruby1.8
arch = i686-linux
sitearch = i686-linux
ruby_version = 1.8
ruby = /usr/bin/ruby1.8
RUBY = $(ruby)
RM = rm -f
MAKEDIRS = mkdir -p
INSTALL = /usr/bin/install -c
INSTALL_PROG = $(INSTALL) -m 0755
INSTALL_DATA = $(INSTALL) -m 644
COPY = cp

#### End of system configuration section. ####

preload = 

libpath = . $(libdir)
LIBPATH =  -L. -L$(libdir)
DEFFILE = 

CLEANFILES = mkmf.log
DISTCLEANFILES = 

extout = 
extout_prefix = 
target_prefix = /sqlite3
LOCAL_LIBS = 
LIBS = $(LIBRUBYARG_SHARED) -lsqlite3  -lpthread -lrt -ldl -lcrypt -lm   -lc
SRCS = backup.c statement.c exception.c database.c sqlite3.c
OBJS = backup.o statement.o exception.o database.o sqlite3.o
TARGET = sqlite3_native
DLLIB = $(TARGET).so
EXTSTATIC = 
STATIC_LIB = 

BINDIR        = $(bindir)
RUBYCOMMONDIR = $(sitedir)$(target_prefix)
RUBYLIBDIR = /home/lord/rails_projects/library/vendor/bundle/ruby/1.8/gems/sqlite3-1.3.5/lib$(target_prefix)
RUBYARCHDIR = /home/lord/rails_projects/library/vendor/bundle/ruby/1.8/gems/sqlite3-1.3.5/lib$(target_prefix)

TARGET_SO     = $(DLLIB)
CLEANLIBS     = $(TARGET).so $(TARGET).il? $(TARGET).tds $(TARGET).map
CLEANOBJS     = *.o *.a *.s[ol] *.pdb *.exp *.bak

all:		$(DLLIB)
static:		$(STATIC_LIB)

clean:
		@-$(RM) $(CLEANLIBS) $(CLEANOBJS) $(CLEANFILES)

distclean:	clean
		@-$(RM) Makefile $(RUBY_EXTCONF_H) conftest.* mkmf.log
		@-$(RM) core ruby$(EXEEXT) *~ $(DISTCLEANFILES)

realclean:	distclean
install: install-so install-rb

install-so: $(RUBYARCHDIR)
install-so: $(RUBYARCHDIR)/$(DLLIB)
$(RUBYARCHDIR)/$(DLLIB): $(DLLIB)
	$(INSTALL_PROG) $(DLLIB) $(RUBYARCHDIR)
install-rb: pre-install-rb install-rb-default
install-rb-default: pre-install-rb-default
pre-install-rb: Makefile
pre-install-rb-default: Makefile
$(RUBYARCHDIR):
	$(MAKEDIRS) $@

site-install: site-install-so site-install-rb
site-install-so: install-so
site-install-rb: install-rb

.SUFFIXES: .c .m .cc .cxx .cpp .C .o

.cc.o:
	$(CXX) $(INCFLAGS) $(CPPFLAGS) $(CXXFLAGS) -c $<

.cxx.o:
	$(CXX) $(INCFLAGS) $(CPPFLAGS) $(CXXFLAGS) -c $<

.cpp.o:
	$(CXX) $(INCFLAGS) $(CPPFLAGS) $(CXXFLAGS) -c $<

.C.o:
	$(CXX) $(INCFLAGS) $(CPPFLAGS) $(CXXFLAGS) -c $<

.c.o:
	$(CC) $(INCFLAGS) $(CPPFLAGS) $(CFLAGS) -c $<

$(DLLIB): $(OBJS) Makefile
	@-$(RM) $@
	$(LDSHARED) -o $@ $(OBJS) $(LIBPATH) $(DLDFLAGS) $(LOCAL_LIBS) $(LIBS)



$(OBJS): ruby.h defines.h
