#******************************************************************************
#
# Makefile - Rules for building the CAN Device LED Switch.
#
# Copyright (c) 2007-2010 Texas Instruments Incorporated.  All rights reserved.
# Software License Agreement
# 
# Texas Instruments (TI) is supplying this software for use solely and
# exclusively on TI's microcontroller products. The software is owned by
# TI and/or its suppliers, and is protected under applicable copyright
# laws. You may not combine this software with "viral" open-source
# software in order to form a larger program.
# 
# THIS SOFTWARE IS PROVIDED "AS IS" AND WITH ALL FAULTS.
# NO WARRANTIES, WHETHER EXPRESS, IMPLIED OR STATUTORY, INCLUDING, BUT
# NOT LIMITED TO, IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
# A PARTICULAR PURPOSE APPLY TO THIS SOFTWARE. TI SHALL NOT, UNDER ANY
# CIRCUMSTANCES, BE LIABLE FOR SPECIAL, INCIDENTAL, OR CONSEQUENTIAL
# DAMAGES, FOR ANY REASON WHATSOEVER.
# 
# This is part of revision 6075 of the EK-LM3S8962 Firmware Package.
#
#******************************************************************************

#
# Defines the part type that this project uses.
#
PART=LM3S2110

#
# The base directory for StellarisWare.
#
ROOT=../../..

#
# Include the common make definitions.
#
include ${ROOT}/makedefs

#
# Where to find header files that do not live in the source directory.
#
IPATH=../../..

#
# The default rule, which causes the CAN Device LED Switch to be built.
#
all: ${COMPILER}
all: ${COMPILER}/can_device_led.axf

#
# The rule to clean out all the build products.
#
clean:
	@rm -rf ${COMPILER} ${wildcard *~}

#
# The rule to create the target directory.
#
${COMPILER}:
	@mkdir ${COMPILER}

#
# Rules for building the CAN Device LED Switch.
#
${COMPILER}/can_device_led.axf: ${COMPILER}/can_device_led.o
${COMPILER}/can_device_led.axf: ${COMPILER}/startup_${COMPILER}.o
${COMPILER}/can_device_led.axf: ${ROOT}/driverlib/${COMPILER}/libdriver.a
${COMPILER}/can_device_led.axf: can_device_led.ld
SCATTERgcc_can_device_led=can_device_led.ld
ENTRY_can_device_led=ResetISR

#
# Include the automatically generated dependency files.
#
ifneq (${MAKECMDGOALS},clean)
-include ${wildcard ${COMPILER}/*.d} __dummy__
endif
