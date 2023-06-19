CFILES = hfs_endian.c makehfs.c newfs_hfs.c
OFILES = $(CFILES:.c=.o)

all: newfs_hfs

newfs_hfs: $(OFILES)
	${CC} ${CFLAGS} ${LDFLAGS} -o newfs_hfs ${OFILES} -lcrypto

install:
	install -d $(DESTDIR)$(PREFIX)/sbin
	install newfs_hfs $(DESTDIR)$(PREFIX)/sbin
	install -d $(DESTDIR)$(PREFIX)/share/man/man8
	install newfs_hfs.8 $(DESTDIR)$(PREFIX)/share/man/man8

clean:
	$(RM) newfs_hfs $(OFILES)

.PHONY : FORCE clean
