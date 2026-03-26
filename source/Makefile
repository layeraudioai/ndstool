NDSTOOL_DATE ?= $(shell date +"%b %e %Y")

NDSTOOL_DATE ?= $(shell date +"%b %e %Y")

CXX := g++
CC  := gcc
CXXFLAGS := -O2 -Wall -Wextra -I. -DNDSTOOL_DATE="\"$(NDSTOOL_DATE)\"" -DPACKAGE_VERSION="\"xbcx\""
CFLAGS   := -O2 -Wall -Wextra -I.
LDFLAGS  := 

TARGET := ../ndstool

SRCS_CPP := banner.cpp \
            crc.cpp \
            elf.cpp \
            hook.cpp \
            logo.cpp \
            ndscreate.cpp \
            ndstool.cpp \
            ndstree.cpp \
            raster.cpp \
            sha1.cpp \
            ndsextract.cpp \
            encryption.cpp \
            header.cpp \
            ndscodes.cpp

SRCS_C   := loadme.c

OBJS     := $(SRCS_CPP:.cpp=.o) $(SRCS_C:.c=.o)

all: $(TARGET)

$(TARGET): $(OBJS)
	$(CXX) $(LDFLAGS) -o $@ $^

%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

%.o: %.c
	$(CC) $(CFLAGS) -c $< -o $@

clean:
	rm -f $(OBJS) $(TARGET)

.PHONY: all clean