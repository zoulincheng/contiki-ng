CONTIKI_PROJECT = border-router
all: $(CONTIKI_PROJECT)

TARGET ?= jn516x

CONTIKI=../../../../..

MAKE_MAC = MAKE_MAC_TSCH
PROJECTDIRS += .. ../tools
PROJECT_SOURCEFILES += rpl-tools.c
PROJECT_SOURCEFILES += slip-bridge.c slip.c

ifeq ($(PREFIX),)
 PREFIX = fd00::1/64
endif

include $(CONTIKI)/Makefile.include

#using XON/XOFF flow control
connect-router-sw:	$(CONTIKI)/tools/tunslip6
	sudo $(CONTIKI)/tools/tunslip6 -X -B 1000000 $(PREFIX)

#using hw flow control
connect-router-hw:	$(CONTIKI)/tools/tunslip6
	sudo $(CONTIKI)/tools/tunslip6 -H -B 1000000 $(PREFIX)

#using no flow control
connect-router-no:	$(CONTIKI)/tools/tunslip6
	sudo $(CONTIKI)/tools/tunslip6 -B 1000000 $(PREFIX)
