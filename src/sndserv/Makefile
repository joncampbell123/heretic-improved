CC = gcc

CFLAGS=	-Wall -Wstrict-prototypes $(COPT.arch)

LIBS=	-lm

OBJS=	soundsrv.o sounds.o wadread.o linux.o


all: sndserver

sndserver:	dep $(OBJS)
		$(CC) $(CFLAGS) $(OBJS) $(LIBS) -o sndserver
		cp sndserver ../

clean:
		rm -f $(OBJS) sndserver ../sndserver .depend *~

dep:
		$(CC) -E -M $(CFLAGS) *.c > .depend

%.o: 		%.c	
		$(CC) $(CFLAGS) -c $< -o $@

ifeq (.depend,$(wildcard .depend))
include .depend
endif
