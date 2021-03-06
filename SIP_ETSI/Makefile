# This Makefile was generated by the Makefile Generator
# of the TTCN-3 Test Executor version CRL 113 200/5 R4C
# for Global Warning (james00@GlobalWarning1) on Fri Feb 19 19:07:18 2016

# Copyright (c) 2000-2015 Ericsson Telecom AB

# The following make commands are available:
# - make, make all      Builds the executable test suite.
# - make archive        Archives all source files.
# - make check          Checks the semantics of TTCN-3 and ASN.1 modules.
# - make clean          Removes all generated files.
# - make compile        Translates TTCN-3 and ASN.1 modules to C++.
# - make dep            Creates/updates dependency list.
# - make executable     Builds the executable test suite.
# - make library        Builds the library archive.
# - make objects        Builds the object files without linking the executable.
#
# Set these variables...
#

# The path of your TTCN-3 Test Executor installation:
# Uncomment this line to override the environment variable.
# TTCN3_DIR = 

# Your platform: (SOLARIS, SOLARIS8, LINUX, FREEBSD or WIN32)
PLATFORM = LINUX

# Your C++ compiler:
# (if you change the platform, you may need to change the compiler)
CXX = g++ 

# Flags for the C++ preprocessor (and makedepend as well):
CPPFLAGS = -D$(PLATFORM) -I$(TTCN3_DIR)/include

# Flags for the C++ compiler:
CXXFLAGS = -Wall  

# Flags for the linker:
LDFLAGS = 

ifeq ($(PLATFORM), WIN32)
# Silence linker warnings.
LDFLAGS += -Wl,--enable-auto-import,--enable-runtime-pseudo-reloc
endif

# Utility to create library files
AR = ar
ARFLAGS = 

# Flags for the TTCN-3 and ASN.1 compiler:
COMPILER_FLAGS = -L 

# Execution mode: (either ttcn3 or ttcn3-parallel)
TTCN3_LIB = ttcn3-parallel

# The path of your libxml2 installation:
# If you do not have your own one, leave it unchanged.
XMLDIR = $(TTCN3_DIR)

# Directory to store the archived source files:
# Note: you can set any directory except ./archive
ARCHIVE_DIR = backup

#
# You may change these variables. Add your files if necessary...
#

# TTCN-3 modules of this project:
TTCN3_MODULES = SIP_CallControl.ttcn SIP_MainModule.ttcn SIP_Messaging.ttcn SIPmsg_PortType.ttcn SIPmsg_Types.ttcn SIP_QueryingCapabilities.ttcn SIP_Registration.ttcn SIP_Steps.ttcn SIP_Templates.ttcn SIP_TypesAndConf.ttcn TCCConversion_Functions.ttcn TCCDateTime_Functions.ttcn TCCInterface_Functions.ttcn

# ASN.1 modules of this project:
ASN1_MODULES =

# C++ source & header files generated from the TTCN-3 & ASN.1 modules of
# this project:
GENERATED_SOURCES = SIP_CallControl.cc SIP_MainModule.cc SIP_Messaging.cc SIPmsg_PortType.cc SIPmsg_Types.cc SIP_QueryingCapabilities.cc SIP_Registration.cc SIP_Steps.cc SIP_Templates.cc SIP_TypesAndConf.cc TCCConversion_Functions.cc TCCDateTime_Functions.cc TCCInterface_Functions.cc
GENERATED_HEADERS = SIP_CallControl.hh SIP_MainModule.hh SIP_Messaging.hh SIPmsg_PortType.hh SIPmsg_Types.hh SIP_QueryingCapabilities.hh SIP_Registration.hh SIP_Steps.hh SIP_Templates.hh SIP_TypesAndConf.hh TCCConversion_Functions.hh TCCDateTime_Functions.hh TCCInterface_Functions.hh

# C/C++ Source & header files of Test Ports, external functions and
# other modules:
USER_SOURCES = SIPmsg_PT.cc TCCConversion.cc TCCDateTime.cc TCCInterface.cc lex.SIP_parse_.c SIP_parse_.tab.c
USER_HEADERS = SIPmsg_PT.hh SIP_parse_.tab.h SIP_parse.h TCCInterface_ip.h

# Object files of this project that are needed for the executable test suite:
OBJECTS = $(GENERATED_OBJECTS) $(USER_OBJECTS)

GENERATED_OBJECTS = SIP_CallControl.o SIP_MainModule.o SIP_Messaging.o SIPmsg_PortType.o SIPmsg_Types.o SIP_QueryingCapabilities.o SIP_Registration.o SIP_Steps.o SIP_Templates.o SIP_TypesAndConf.o TCCConversion_Functions.o TCCDateTime_Functions.o TCCInterface_Functions.o

USER_OBJECTS = SIPmsg_PT.o TCCConversion.o TCCDateTime.o TCCInterface.o lex.SIP_parse_.o SIP_parse_.tab.o

# Other files of the project (Makefile, configuration files, etc.)
# that will be added to the archived source files:
OTHER_FILES = Makefile

# The name of the executable test suite:
EXECUTABLE = SIP_CallControl



LIBRARY = lib$(EXECUTABLE).a

TARGET = $(EXECUTABLE)

#
# Do not modify these unless you know what you are doing...
# Platform specific additional libraries:
#
SOLARIS_LIBS = -lsocket -lnsl -lxml2
SOLARIS8_LIBS = -lsocket -lnsl -lxml2
LINUX_LIBS = -lxml2 -lpthread -lrt
FREEBSD_LIBS = -lxml2
WIN32_LIBS = -lxml2

#
# Rules for building the executable...
#

all: $(TARGET) ;

executable: $(EXECUTABLE) ;

library: $(LIBRARY) ;

objects: $(OBJECTS) compile;

$(EXECUTABLE): $(OBJECTS)
	if $(CXX) $(LDFLAGS) -o $@ $(OBJECTS) \
	-L$(TTCN3_DIR)/lib -l$(TTCN3_LIB) \
	-L$(OPENSSL_DIR)/lib -lcrypto \
	-L$(XMLDIR)/lib $($(PLATFORM)_LIBS); \
	then : ; else $(TTCN3_DIR)/bin/titanver $(OBJECTS); exit 1; fi

$(LIBRARY): $(OBJECTS)
	$(AR) -r $(ARFLAGS) $(LIBRARY) $(OBJECTS)

.cc.o .c.o:
	$(CXX) -c $(CPPFLAGS) $(CXXFLAGS) -o $@ $<

$(GENERATED_SOURCES) $(GENERATED_HEADERS): compile
	@if [ ! -f $@ ]; then rm -f compile; $(MAKE) compile; fi

check: $(TTCN3_MODULES) $(ASN1_MODULES)
	$(TTCN3_DIR)/bin/compiler -s $(COMPILER_FLAGS) \
	$(TTCN3_MODULES) $(PREPROCESSED_TTCN3_MODULES) $(ASN1_MODULES)

compile: $(TTCN3_MODULES) $(ASN1_MODULES)
	$(TTCN3_DIR)/bin/compiler $(COMPILER_FLAGS) \
	$(TTCN3_MODULES) $(ASN1_MODULES) - $?
	touch $@

clean:
	-rm -f $(EXECUTABLE) $(LIBRARY) $(OBJECTS) $(GENERATED_HEADERS) \
	$(GENERATED_SOURCES) compile \
	tags *.log

dep: $(GENERATED_SOURCES) $(USER_SOURCES) ;
	makedepend $(CPPFLAGS) -DMAKEDEPEND_RUN $(GENERATED_SOURCES) $(USER_SOURCES)

archive:
	mkdir -p $(ARCHIVE_DIR)
	tar -cvhf - $(TTCN3_MODULES) $(ASN1_MODULES) \
	$(USER_HEADERS) $(USER_SOURCES) $(OTHER_FILES) \
	| gzip >$(ARCHIVE_DIR)/`basename $(TARGET) .exe`-`date '+%y%m%d-%H%M'`.tgz

diag:
	$(TTCN3_DIR)/bin/compiler -v 2>&1
	$(TTCN3_DIR)/bin/mctr_cli -v 2>&1
	$(CXX) -v 2>&1
	$(AR) -V 2>&1
	@echo TTCN3_DIR=$(TTCN3_DIR)
	@echo OPENSSL_DIR=$(OPENSSL_DIR)
	@echo XMLDIR=$(XMLDIR)
	@echo PLATFORM=$(PLATFORM)

#
# Add your rules here if necessary...
#

