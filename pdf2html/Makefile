CFLAGS= -O3 -Wall -funroll-loops
CC=gcc
SOURCES_LIB= pbm2eps9.c printer.c
OBJS= $(SOURCES_LIB:.c=.o)

all: pbm2png pbm2eps9 

pbm2png:
	$(CC) $(CFLAGS) -s -o pbm2png pbm2png.c -lpng

pbm2eps9: $(OBJS)
#	$(CC) $(CFLAGS) -c -o pbm2eps9.o pbm2eps9.c
#	$(CC) $(CFLAGS) -c -o printer.o printer.c
	$(CC) -s -o pbm2eps9 pbm2eps9.o printer.o

%.o: %.c
	$(CC) -Wall -c $<

.depend:
	$(CC) -MM ${SOURCES_LIB} > $@

clean:
	rm -f *.o pbm2png pbm2eps9

.PHONY: clean all
