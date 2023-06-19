CFILES = fsck_hfs.c utilities.c cache.c fsck_messages.c fsck_debug.c fsck_hfs_strings.c fsck_strings.c
OFILES = $(CFILES:.c=.o)
CFLAGS += -DTRUE=1 -DFALSE=0 -DDEBUG_BUILD=0

all: fsck_hfs

fsck_hfs: $(OFILES) dfalib/libdfa.a
	  $(CC) $(CFLAGS) $(LDFLAGS) $(OFILES) dfalib/libdfa.a -o fsck_hfs -lbsd -lpthread

dfalib/libdfa.a: FORCE
	$(MAKE) -C dfalib -f Makefile libdfa.a

install:
	install -d $(DESTDIR)$(PREFIX)/sbin
	install fsck_hfs $(DESTDIR)$(PREFIX)/sbin
	install -d $(DESTDIR)$(PREFIX)/share/man/man8
	install fsck_hfs.8 $(DESTDIR)$(PREFIX)/share/man/man8

clean:
	$(RM) fsck_hfs $(OFILES)
	$(MAKE) -C dfalib -f Makefile clean

.PHONY : FORCE clean
