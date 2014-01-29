#$L$
# Copyright (C) 2012 Ridgerun (http://www.ridgerun.com).
##$L$

-include patches/arch/Makefile
-include patches/mach/Makefile
include ../../bsp/classes/rrsdk.class

#====================================================================================================
# DM81XX Platforms
#====================================================================================================
ifeq ($(CONFIG_PROPRIETARY_TI_GRAPHICS_SDK_DM81XX),y)
SGXSDK_PLATFORM=dm81xx
SGXSDK_NAME=Graphics_SDK_4_04_00_02
SGXSDK_TARGETS=drivers_sgx demos_sgx
SGXSDK_PATHINSDK=$(DEVDIR)/proprietary/graphics-sdk-4_04_00_02
OMAPES=6.x
SGXSDK_COPY_EXCLUSIONS_PATTERNS=

# This is the file we test to see if we have the right SGXSDK
SGXSDK_VERIFICATION_FILE=gfx_dbg_es6.x/ded813fc6c4273347b175a6454426e2f.md5
endif

INIT_SCRIPT=sgxsdk.init
INIT_SCRIPT_LEVEL=90

# We are an gsxsdk 
include $(CLASSES)/sgxsdk.class

cmdline: sgxsdk_cmdline
