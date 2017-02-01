#
# Makefile for MacOSX
#
# e.g.
#   CFLAGS=-g OPENSSL=/usr/local/Cellar/openssl/1.0.2h_1 make

PREFIX ?= /usr/local/Cellar/sscep/20170201
BINDIR = $(PREFIX)/bin
MANDIR = $(PREFIX)/man

CC	= gcc
OPENSSL ?= /usr/local/openssl
CPPFLAGS = -I $(OPENSSL)/include 
CFLAGS	+= -Wall -O

LDFLAGS = -L$(OPENSSL)
LDLIBS = -lcrypto

MAN	= sscep.8
PROG	= sscep
OBJS    = sscep.o init.o net.o sceputils.o pkcs7.o ias.o fileutils.o configuration.o engine.o

all: $(PROG)

$(PROG): $(OBJS)
	$(CC) $(CFLAGS) -o $(PROG) $(OBJS) $(LDLIBS) $(LDFLAGS)

clean:
	rm -f $(PROG) $(OBJS) $(MAN) core

install: all
	echo "Installing"
	install -d $(BINDIR)
	install sscep $(BINDIR)

package:

