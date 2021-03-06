# =================================================================================================
# ADOBE SYSTEMS INCORPORATED
# Copyright 2013 Adobe Systems Incorporated
# All Rights Reserved
#
# NOTICE: Adobe permits you to use, modify, and distribute this file in accordance with the terms
# of the Adobe license agreement accompanying it.
# =================================================================================================

CURRDIR := $(shell dirname "$(realpath $(lastword $(MAKEFILE_LIST)))")
arch=$(shell getconf LONG_BIT)
CMAKE="$(CURRDIR)/../../tools/cmake/bin/cmake"
TOOLCHAIN="$(CURRDIR)/../../build/shared/ToolchainGCC.cmake"

# Default target executed when no arguments are given to make.
default_target: all


# Export for cmake binaries

# target to generate make files using cmake
Debug32: DIR=./gcc/i80386linux/Debug/
Debug32:
ifeq ($(arch),32)
	mkdir -p $(DIR) || echo "Unable to create Directory $(DIR)"; \
	cd $(DIR) || echo "unable to Change Directory $(DIR)" ; \
	${MAKE} -C "$(CURRDIR)/../../build/" StaticDebug32 ; \
	$(CMAKE) -D CMAKE_CL_64=0 -DCMAKE_BUILD_TYPE=Debug -G "Unix Makefiles" -DCMAKE_TOOLCHAIN_FILE=$(TOOLCHAIN) ../../../cmake
	${MAKE} -C $(DIR)
endif

Release32: DIR=./gcc/i80386linux/Release/
Release32:
ifeq ($(arch),32)
	mkdir -p $(DIR) || echo "Unable to create Directory $(DIR)"; \
	cd $(DIR) || echo "unable to Change Directory $(DIR)" ; \
	${MAKE} -C "$(CURRDIR)/../../build/" StaticRelease32 ; \
	$(CMAKE) -D CMAKE_CL_64=0 -DCMAKE_BUILD_TYPE=Release -G "Unix Makefiles"  -DCMAKE_TOOLCHAIN_FILE=$(TOOLCHAIN) ../../../cmake
	${MAKE} -C $(DIR)
endif

Debug64: DIR=./gcc/i80386linux_x64/Debug/
Debug64:
ifeq ($(arch),64)
	mkdir -p $(DIR) || echo "Unable to create Directory $(DIR)"; \
	cd $(DIR) || echo "unable to Change Directory $(DIR)" ; \
	${MAKE} -C "$(CURRDIR)/../../build/" StaticDebug64 ; \
	$(CMAKE) -D CMAKE_CL_64=1 -DCMAKE_BUILD_TYPE=Debug -G "Unix Makefiles"  -DCMAKE_TOOLCHAIN_FILE=$(TOOLCHAIN) ../../../cmake
	${MAKE} -C $(DIR)
endif

Release64: DIR=./gcc/i80386linux_x64/Release/
Release64:
ifeq ($(arch),64)
	mkdir -p $(DIR) || echo "Unable to create Directory $(DIR)"; \
	cd $(DIR) || echo "unable to Change Directory $(DIR)" ; \
	${MAKE} -C "$(CURRDIR)/../../build/" StaticRelease64 ; \
	$(CMAKE) -D CMAKE_CL_64=1 -DCMAKE_BUILD_TYPE=Release -G "Unix Makefiles"  -DCMAKE_TOOLCHAIN_FILE=$(TOOLCHAIN) ../../../cmake
	${MAKE} -C $(DIR)
endif

all: Debug32 Release32 Debug64 Release64

clean:
	test -d "$(CURRDIR)/../target/i80386linux/" &&  rm -rf "$(CURRDIR)/../target/i80386linux/"; \
	test -d "$(CURRDIR)/../target/i80386linux_x64/" &&  rm -rf "$(CURRDIR)/../target/i80386linux_x64"/; \
	test -d "$(CURRDIR)/gcc" && rm -rf "$(CURRDIR)/gcc"; \
	test -d "$(CURRDIR)/cmake/DumpFile/build" && rm -rf "$(CURRDIR)/cmake/DumpFile/build"; \
	test -d "$(CURRDIR)/cmake/DumpFile/build_x64" && rm -rf "$(CURRDIR)/cmake/DumpFile/build_64"; \
	test -d "$(CURRDIR)/cmake/DumpScannedXMP/build" && rm -rf "$(CURRDIR)/cmake/DumpScannedXMP/build"; \
	test -d "$(CURRDIR)/cmake/DumpScannedXMP/build_x64" && rm -rf "$(CURRDIR)/cmake/DumpScannedXMP/build_x64"; \
	test -d "$(CURRDIR)/cmake/ReadingXMP/build" && rm -rf "$(CURRDIR)/cmake/ReadingXMP/build"; \
	test -d "$(CURRDIR)/cmake/ReadingXMP/build_x64" && rm -rf "$(CURRDIR)/cmake/ReadingXMP/build_x64"; \
	test -d "$(CURRDIR)/cmake/XMPCommand/build" && rm -rf "$(CURRDIR)/cmake/XMPCommand/build" ; \
	test -d "$(CURRDIR)/cmake/XMPCommand/build_x64" && rm -rf "$(CURRDIR)/cmake/XMPCommand/build_x64" ; \
	test -d "$(CURRDIR)/cmake/XMPFilesCoverage/build" && rm -rf "$(CURRDIR)/cmake/XMPFilesCoverage/build"; \
	test -d "$(CURRDIR)/cmake/XMPFilesCoverage/build_x64" && rm -rf "$(CURRDIR)/cmake/XMPFilesCoverage/build_x64"; \
	test -d "$(CURRDIR)/cmake/CustomSchema/build" && rm -rf "$(CURRDIR)/cmake/CustomSchema/build"; \
	test -d "$(CURRDIR)/cmake/CustomSchema/build_x64" && rm -rf "$(CURRDIR)/cmake/CustomSchema/build_x64"; \
	test -d "$(CURRDIR)/cmake/DumpMainXMP/build" && rm -rf "$(CURRDIR)/cmake/DumpMainXMP/build"; \
	test -d "$(CURRDIR)/cmake/DumpMainXMP/build_x64" && rm -rf "$(CURRDIR)/cmake/DumpMainXMP/build_x64"; \
	test -d "$(CURRDIR)/cmake/ModifyingXMP/build" && rm -rf "$(CURRDIR)/cmake/ModifyingXMP/build"; \
	test -d "$(CURRDIR)/cmake/ModifyingXMP/build_x64" && rm -rf "$(CURRDIR)/cmake/ModifyingXMP/build_x64"; \
	test -d "$(CURRDIR)/cmake/XMPCoreCoverage/build" && rm -rf "$(CURRDIR)/cmake/XMPCoreCoverage/build"; \
	test -d "$(CURRDIR)/cmake/XMPCoreCoverage/build_x64" && rm -rf "$(CURRDIR)/cmake/XMPCoreCoverage/build_x64"; \
	test -d "$(CURRDIR)/cmake/XMPIterations/build" && rm -rf "$(CURRDIR)/cmake/XMPIterations/build"; \
	test -d "$(CURRDIR)/cmake/XMPIterations/build_x64" && rm -rf "$(CURRDIR)/cmake/XMPIterations/build_x64"; \
	echo "Clean Success"  
