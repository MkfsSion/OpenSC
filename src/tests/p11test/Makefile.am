include $(top_srcdir)/win32/ltrc.inc

MAINTAINERCLEANFILES = $(srcdir)/Makefile.in
EXTRA_DIST = Makefile.mak

if ENABLE_OPENSSL
if ENABLE_CMOCKA
noinst_PROGRAMS = p11test
endif
endif

noinst_HEADERS = p11test_loader.h p11test_case_common.h \
	p11test_case_readonly.h p11test_case_multipart.h \
	p11test_case_mechs.h p11test_case_ec_sign.h \
	p11test_case_usage.h p11test_case_wait.h \
	p11test_case_pss_oaep.h p11test_helpers.h \
	p11test_case_ec_derive.h p11test_case_interface.h \
	p11test_case_wrap.h p11test_case_secret.h \
	p11test_common.h

AM_CPPFLAGS = -I$(top_srcdir)/src

p11test_SOURCES = p11test.c p11test_loader.c \
	p11test_case_common.c \
	p11test_case_readonly.c \
	p11test_case_multipart.c \
	p11test_case_mechs.c \
	p11test_case_ec_sign.c \
	p11test_case_ec_derive.c \
	p11test_case_usage.c \
	p11test_case_wait.c \
	p11test_case_pss_oaep.c \
	p11test_case_interface.c \
	p11test_case_wrap.c \
	p11test_case_secret.c \
	p11test_helpers.c
p11test_CFLAGS = $(OPTIONAL_OPENSSL_CFLAGS) $(CMOCKA_CFLAGS)
p11test_LDADD = $(OPTIONAL_OPENSSL_LIBS) $(CMOCKA_LIBS)

if WIN32
p11test_SOURCES += $(top_builddir)/win32/versioninfo.rc
endif
