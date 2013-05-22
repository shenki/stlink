PRG := st-util
OBJS = gdb-remote.o gdb-server.o elfsym.o

CFLAGS+=-g -Wall -Werror -std=gnu99 -I../src
LDFLAGS=-L.. -lstlink

# libusb location
LDFLAGS+=`pkg-config --libs libusb-1.0` -lelfCFLAGS+=`pkg-config --cflags libusb-1.0`

all: $(PRG)

$(PRG): $(OBJS) ../libstlink.a
	$(CC) -o $@  $^ $(LDFLAGS)

clean:
	rm -rf $(OBJS)
	rm -rf $(PRG)

.PHONY: clean all
