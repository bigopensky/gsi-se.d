### Makefile --- 
## Author:  alex.weidauer@huckfinn.de
## Version: $Id: Makefile,v 0.1 2013/10/02 14:41:26 huckfinn Exp $

LPATH   = -L/usr/lib -L/usr/local/lib -L.
IPATH   = -I/usr/include/ -I/usr/local/include
CFLAGS  = -std=c99 -pedantic
LLINALG = -lgsl -lblas
LGDAL   = -lgdal

all:	build/gpc-trfm 

clean:
	rm build/*

build/gpc-trfm: gpc-trfm.c alg.c
	gcc  $(IPATH) $(LPATH) $(LLINALG) $(CFLAGS) -o build/gpc-trfm gpc-trfm.c alg.c

alg.o: alg.c
	gcc $(IPATH) $(LPATH) $(LLINALG)  $(CFLAGS) -c alg.c 

test:
	build/gpc-trfm -s "|" -p 1 0 10 0 -p 0 1 0 10 -p 1 1 10 10 -m
	build/gpc-trfm -d -i -s "|" -p 1 0 10 0 -p 0 1 0 10 -p 1 1 10 10 -c 1 1 -c 1 0
	build/gpc-trfm -s "|" -p 1 0 10 0 -p 0 1 0 10 -p 1 1 10 10 -c 1 1 -c 1 0

