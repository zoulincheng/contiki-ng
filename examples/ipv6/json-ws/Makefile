CONTIKI=../../..

PROJECT_SOURCEFILES += json-ws.c

ifdef WITH_COSM
 CFLAGS += -DWITH_COSM=1
endif

ifdef WITH_UDP
 CFLAGS += -DWITH_UDP=1
 PROJECT_SOURCEFILES += json-ws-udp.c
endif

MODULES += os/lib/json os/net/app-layer/httpd-ws

ifeq ($(TARGET),)
 -include Makefile.target
endif

ifneq ($(TARGET),)
all: websense-$(TARGET)
endif

include $(CONTIKI)/Makefile.include
