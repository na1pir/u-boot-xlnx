#
# Copyright (c) 2007
# Nobuhiro Iwamatsu <iwamatsu@nigauri.org>
#
# SPDX-License-Identifier:	GPL-2.0+
#


obj-$(CONFIG_CMD_BOOTM) += bootm.o
ifeq ($(CONFIG_CPU_SH2),y)
obj-y	+= time_sh2.o
else
obj-y	+= time.o
endif
obj-$(CONFIG_CMD_SH_ZIMAGEBOOT) += zimageboot.o

udivsi3-y			:= udivsi3_i4i-Os.o

ifneq ($(CONFIG_CC_OPTIMIZE_FOR_SIZE),y)
udivsi3-$(CONFIG_CPU_SH3)	:= udivsi3_i4i.o
udivsi3-$(CONFIG_CPU_SH4)	:= udivsi3_i4i.o
endif
udivsi3-y			+= udivsi3.o

lib-$(CONFIG_USE_PRIVATE_LIBGCC) += movmem.o ashldi3.o ashrdi3.o lshrdi3.o \
				    ashlsi3.o ashrsi3.o ashiftrt.o lshrsi3.o \
				    udiv_qrnnd.o $(udivsi3-y)
