########################################################################### ###
#@Copyright     Copyright (c) Imagination Technologies Ltd. All Rights Reserved
#@License       Dual MIT/GPLv2
# 
# The contents of this file are subject to the MIT license as set out below.
# 
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
# 
# The above copyright notice and this permission notice shall be included in
# all copies or substantial portions of the Software.
# 
# Alternatively, the contents of this file may be used under the terms of
# the GNU General Public License Version 2 ("GPL") in which case the provisions
# of GPL are applicable instead of those above.
# 
# If you wish to allow use of your version of this file only under the terms of
# GPL, and not to allow others to use your version of this file under the terms
# of the MIT license, indicate your decision by deleting the provisions above
# and replace them with the notice and other provisions required by GPL as set
# out in the file called "GPL-COPYING" included in this distribution. If you do
# not delete the provisions above, a recipient may use your version of this file
# under the terms of either the MIT license or GPL.
# 
# This License is also included in this distribution in the file called
# "MIT-COPYING".
# 
# EXCEPT AS OTHERWISE STATED IN A NEGOTIATED AGREEMENT: (A) THE SOFTWARE IS
# PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING
# BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR
# PURPOSE AND NONINFRINGEMENT; AND (B) IN NO EVENT SHALL THE AUTHORS OR
# COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER
# IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN
# CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
#   
### ###########################################################################

ccflags-y = -DLINUX -D__linux__ -DANDROID -DPVR_BUILD_DIR="\"omap4430_android\""
ccflags-$(CONFIG_PVR_SGXCORE_540) += -Idrivers/gpu/pvr -Idrivers/gpu/pvr/omap4 -Idrivers/video/omap2
ccflags-$(CONFIG_PVR_SGXCORE_530) += -Idrivers/gpu/pvr -Idrivers/gpu/pvr/omap3 -Idrivers/video/omap2
ccflags-y += \
	-DSUPPORT_SGX \
	-DTRANSFER_QUEUE \
	-DSGX_DYNAMIC_TIMING_INFO \
	-DSUPPORT_HW_RECOVERY \
	-DLDM_PLATFORM \
	-DSUPPORT_SGX_NEW_STATUS_VALS \
	-DSUPPORT_SGX_HWPERF \
	-DSYS_USING_INTERRUPTS \
	-DPVR_SECURE_HANDLES \
	-DPVR_LINUX_USING_WORKQUEUES \
	-DPVR_LINUX_MISR_USING_PRIVATE_WORKQUEUE \
	-DPVR_LINUX_TIMERS_USING_WORKQUEUES \
	-DSYS_CUSTOM_POWERLOCK_WRAP \
	-DSUPPORT_MEMINFO_IDS \
	-DDISPLAY_CONTROLLER=omaplfb \
	-DPVRSRV_MODNAME="\"pvrsrvkm\"" \
	-DPVR_LDM_DRIVER_REGISTRATION_NAME="\"pvrsrvkm\"" \
	-DSUPPORT_DC_CMDCOMPLETE_WHEN_NO_LONGER_DISPLAYED \
	-DSUPPORT_LARGE_GENERAL_HEAP \
	-DPVR_NO_OMAP_TIMER \
	-Idrivers/gpu/pvr/sgx

ccflags-$(CONFIG_PVR_SGXCORE_540) += \
	-DSGX540 -DSUPPORT_SGX540 \
	-DSGX_CORE_REV=120

ccflags-$(CONFIG_PVR_SGXCORE_530) += \
	-DSGX530 -DSUPPORT_SGX530 \
	-DSGX_CORE_REV=125 \
	-DSYS_OMAP3430_PIN_MEMORY_BUS_CLOCK

ccflags-$(CONFIG_PVR_BUILD_RELEASE) += \
	-DPVR_BUILD_TYPE="\"release\"" -DRELEASE

ccflags-$(CONFIG_PVR_BUILD_DEBUG) += \
	-DPVR_BUILD_TYPE="\"debug\"" -DDEBUG

ccflags-$(CONFIG_PVR_NEED_PVR_DPF) += -DPVRSRV_NEED_PVR_DPF -DPVRSRV_NEED_PVR_TRACE
ccflags-$(CONFIG_PVR_NEED_PVR_ASSERT) += -DPVRSRV_NEED_PVR_ASSERT

ccflags-$(CONFIG_PVR_DEBUG_MEMORY) += \
	-DDEBUG_LINUX_MEMORY_ALLOCATIONS \
	-DDEBUG_LINUX_MEM_AREAS \
	-DDEBUG_LINUX_MMAP_AREAS

ccflags-$(CONFIG_PVR_DEBUG_BRIDGE_KM) += -DDEBUG_BRIDGE_KM
ccflags-$(CONFIG_PVR_DEBUG_TRACE_BRIDGE_KM) += -DDEBUG_TRACE_BRIDGE_KM
ccflags-$(CONFIG_PVR_DEBUG_BRIDGE_KM_DISPATCH_TABLE) += -DDEBUG_BRIDGE_KM_DISPATCH_TABLE

ccflags-$(CONFIG_PVR_PERCONTEXT_PB) += -DSUPPORT_PERCONTEXT_PB
ccflags-$(CONFIG_PVR_SGX_LOW_LATENCY_SCHEDULING) += -DSUPPORT_SGX_LOW_LATENCY_SCHEDULING
ccflags-$(CONFIG_PVR_ACTIVE_POWER_MANAGEMENT) += -DSUPPORT_ACTIVE_POWER_MANAGEMENT
ccflags-$(CONFIG_PVR_ACTIVE_POWER_MANAGEMENT) += \
	-DSYS_SGX_ACTIVE_POWER_LATENCY_MS=CONFIG_PVR_ACTIVE_POWER_LATENCY_MS

ccflags-$(CONFIG_PVR_USSE_EDM_STATUS_DEBUG) += -DPVRSRV_USSE_EDM_STATUS_DEBUG
ccflags-$(CONFIG_PVR_DUMP_MK_TRACE) += -DPVRSRV_DUMP_MK_TRACE

ccflags-$(CONFIG_PVR_PDUMP) += \
	-DPDUMP -DSUPPORT_DBGDRV_EVENT_OBJECTS -DSUPPORT_PDUMP_MULTI_PROCESS

pvrsrvkm-y += \
	osfunc.o \
	mutils.o \
	mmap.o \
	module.o \
	pdump.o \
	proc.o \
	pvr_bridge_k.o \
	pvr_debug.o \
	mm.o \
	mutex.o \
	event.o \
	osperproc.o \
	buffer_manager.o \
	devicemem.o \
	deviceclass.o \
	handle.o \
	hash.o \
	lists.o \
	mem.o \
	mem_debug.o \
	metrics.o \
	osfunc_common.o \
	pdump_common.o \
	perproc.o \
	power.o \
	pvrsrv.o \
	queue.o \
	ra.o \
	refcount.o \
	resman.o \
	bridged_support.o \
	bridged_pvr_bridge.o \
	sgx/bridged_sgx_bridge.o \
	sgx/sgxinit.o \
	sgx/sgxpower.o \
	sgx/sgxreset.o \
	sgx/sgxutils.o \
	sgx/sgxkick.o \
	sgx/sgxtransfer.o \
	sgx/mmu.o \
	sgx/pb.o

pvrsrvkm-$(CONFIG_PVR_SGXCORE_530) += \
	omap3/sysconfig.o \
	omap3/sysutils.o

pvrsrvkm-$(CONFIG_ION_OMAP) += ion.o

omaplfb-y := \
	omaplfb/omaplfb_displayclass.o \
	omaplfb/omaplfb_linux.o

obj-$(CONFIG_PVR_SGX) += pvrsrvkm.o
obj-$(CONFIG_PVR_SGX) += omaplfb.o
