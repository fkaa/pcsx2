#  _____     ___ ____
#   ____|   |    ____|      PSX2 OpenSource Project
#  |     ___|   |____       (C)2002, David Ryan ( Oobles@hotmail.com )
#  ------------------------------------------------------------------------

# Generated automatically from Makefile.in by configure.
#.SUFFIXES: .S .c .o .s .elf .irx

#  ------------------------------------------------------------------------
#  COMPILERS

IOPCC = iop-gcc
IOPAR = iop-ar
IOPLD = iop-ld
IOPAS = iop-as
EECC  = ee-gcc
EEAR  = ee-ar
EELD  = ee-gcc


#  ------------------------------------------------------------------------
#  DIRECTORY PATHS & FLAGS


EECFLAGS  = -O2 -fomit-frame-pointer -mips3 -EL -nostartfiles -G0 -D_EE
EEINCLUDES = -I. -Iinclude -I$(PS2LIB)/common/include -I$(PS2LIB)/ee/include


#  ------------------------------------------------------------------------
#  PROJECTS TO BUILD

all: intro


#  ------------------------------------------------------------------------
#  KERNEL BUILD INSTRUCTIONS

LDFLAGS = -L$(PS2LIB)/ee/lib 
LDADD   = -lmc -lpad -lc -lkernel -lm
OBJECTS = intro.o eedebug.o crt0.o romdir.o
DEST    = ../build/INTRO

intro: $(OBJECTS)
	$(EELD) -T linkfile $(EECFLAGS) $(OBJECTS) $(LDFLAGS) $(LDADD) -o $(DEST)

%.o: %.c
	$(EECC) $(EEINCLUDES) $(EECFLAGS) -o $@ -c $<

%.o: %.s
	$(EECC) $(EEINCLUDES) $(EECFLAGS) -o $@ -c $<


clean:
	rm -f $(OBJECTS) $(DEST)



