CXX      := g++
CXXFLAGS := -O2 -Wall -Wextra
LDFLAGS  := -static

# Definitions for version and build date used in ndstool.cpp
VERSION := 2.1.2
DATE    := $(shell date +%Y%m%d)
CXXFLAGS += -DPACKAGE_VERSION=\"$(VERSION)\" -DNDSTOOL_DATE=\"$(DATE)\"

# Source files inferred from the includes in ndstool.cpp and ndscreate.cpp
SRCS := ndstool.cpp \
        ndscreate.cpp \
        ndsextract.cpp \
        sha1.cpp \
        hook.cpp \
        encryption.cpp \
        banner.cpp \
        logo.cpp \
        raster.cpp \
        ndstree.cpp \
        elf.cpp \
        loadme.cpp \
        crc.cpp

OBJS := $(SRCS:.cpp=.o)
TARGET := ndstool

# Main rules
all: $(TARGET)

$(TARGET): $(OBJS)
	$(CXX) $(LDFLAGS) -o $@ $(OBJS)

%.o: %.cpp
	$(CXX) $(CXXFLAGS) -c $< -o $@

clean:
	rm -f $(OBJS) $(TARGET) $(TARGET).exe

.PHONY: all clean