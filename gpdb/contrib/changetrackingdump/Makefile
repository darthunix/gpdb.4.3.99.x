PROGRAM = changetrackingdump
OBJS    = changetrackingdump.o ../../src/port/sprompt.o ../../src/backend/utils/hash/pg_crc.o ../../src/backend/utils/hash/crc32c.o

PG_CPPFLAGS = -I$(libpq_srcdir)
PG_LIBS = $(libpq_pgport)

ifdef USE_PGXS
PGXS := $(shell pg_config --pgxs)
include $(PGXS)
else
subdir = contrib/changetrackingdump
top_builddir = ../..
include $(top_builddir)/src/Makefile.global
include $(top_srcdir)/contrib/contrib-global.mk
endif
ifneq ($(PORTNAME), win32)
override CFLAGS += $(PTHREAD_CFLAGS) -pthread
endif

