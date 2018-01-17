---
UID: NS:pepfx._PEP_KERNEL_INFORMATION_STRUCT_V3
title: _PEP_KERNEL_INFORMATION_STRUCT_V3
author: windows-driver-content
description: The PEP_KERNEL_INFORMATION_STRUCT_V3 structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx).
old-location: kernel\pep_kernel_information_struct_v3.htm
old-project: kernel
ms.assetid: AA3E273F-FCC0-4633-8A4C-194DA1C0E0D7
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: _PEP_KERNEL_INFORMATION_STRUCT_V3, *PPEP_KERNEL_INFORMATION_STRUCT_V3, PEP_KERNEL_INFORMATION_STRUCT_V3, PEP_KERNEL_INFORMATION, *PPEP_KERNEL_INFORMATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PEP_KERNEL_INFORMATION_STRUCT_V3
req.alt-loc: pepfx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: *PPEP_KERNEL_INFORMATION_STRUCT_V3, PEP_KERNEL_INFORMATION_STRUCT_V3
---

# _PEP_KERNEL_INFORMATION_STRUCT_V3 structure



## -description
The <b>PEP_KERNEL_INFORMATION_STRUCT_V3</b> structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).



## -syntax

````
typedef struct _PEP_KERNEL_INFORMATION_STRUCT_V3 {
  USHORT                                   Version;
  USHORT                                   Size;
  POHANDLE                                 Plugin;
  PPOFXCALLBACKREQUESTWORKER               RequestWorker;
  PPOFXCALLBACKENUMERATEUNMASKEDINTERRUPTS EnumerateUnmaskedInterrupts;
  PPOFXCALLBACKPROCESSORHALT               ProcessorHalt;
  PPOFXCALLBACKREQUESTINTERRUPT            RequestInterrupt;
  PPOFXCALLBACKCRITICALRESOURCE            TransitionCriticalResource;
  PPOFXCALLBACKPROCESSORIDLEVETO           ProcessorIdleVeto;
  PPOFXCALLBACKPLATFORMIDLEVETO            PlatformIdleVeto;
  PPOFXCALLBACKUPDATEPROCESSORIDLESTATE    UpdateProcessorIdleState;
  PPOFXCALLBACKUPDATEPLATFORMIDLESTATE     UpdatePlatformIdleState;
  PPOFXCALLBACKREQUESTCOMMON               RequestCommon;
} PEP_KERNEL_INFORMATION_STRUCT_V3, *PPEP_KERNEL_INFORMATION_STRUCT_V3;
````


## -struct-fields

### -field Version

The current version number for this structure. Set this member to <b>PEP_KERNEL_INFORMATION_VERSION</b>.


### -field Size

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>PEP_KERNEL_INFORMATION</b>).


### -field Plugin

The handle assigned to the PEP's registration with PoFx. PoFx sets the value of this member. The PEP uses this handle in calls to the <a href="..\pepfx\nc-pepfx-pofxcallbackrequestworker.md">RequestWorker</a> routine.


### -field RequestWorker

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackrequestworker.md">RequestWorker</a> routine. PoFx sets the value of this member. The <b>RequestWorker</b> routine is implemented by PoFx. The PEP calls this routine to request the use of a worker thread from the operating system.


### -field EnumerateUnmaskedInterrupts

A pointer to an <a href="..\pepfx\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md">EnumerateUnmaskedInterrupts</a> routine. PoFx sets the value of this member. The <b>EnumerateUnmaskedInterrupts</b> routine is implemented by PoFx. The PEP calls this routine to request information about the unmasked interrupts.


### -field ProcessorHalt

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackprocessorhalt.md">ProcessorHalt</a> routine. PoFx sets the value of this member. The <b>ProcessorHalt</b> routine is implemented by PoFx. The PEP calls this routine to prepare the current processor to enter the halted state.


### -field RequestInterrupt

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackrequestinterrupt.md">RequestInterrupt</a> routine. PoFx sets the value of this member. The <b>RequestInterrupt</b> routine is implemented by PoFx. The PEP calls this routine to replay an edge-triggered interrupt that might have been lost after the hardware platform entered a low-power system state.


### -field TransitionCriticalResource

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackcriticalresource.md">TransitionCriticalResource</a> routine. PoFx sets the value of this member. The <b>TransitionCriticalResource</b> routine is implemented by PoFx. The PEP calls this routine to transition critical system resources to the idle condition.


### -field ProcessorIdleVeto

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackprocessoridleveto.md">ProcessorIdleVeto</a> routine. PoFx sets the value of this member. The <b>ProcessorIdleVeto</b> routine is implemented by PoFx. The PEP calls this routine to increment or decrement the veto count for a pending transition to a processor idle state.


### -field PlatformIdleVeto

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackplatformidleveto.md">PlatformIdleVeto</a> routine. PoFx sets the value of this member. The <b>PlatformIdleVeto</b> routine is implemented by PoFx. The PEP calls this routine to increment or decrement the veto count for a pending transition to a platform idle state.


### -field UpdateProcessorIdleState

A pointer to an <a href="..\pepfx\nc-pepfx-pofxcallbackupdateprocessoridlestate.md">UpdateProcessorIdleState</a> routine. PoFx sets the value of this member. The <b>UpdateProcessorIdleState</b> routine is implemented by PoFx. The PEP calls this routine to update the properties of the specified processor idle state.


### -field UpdatePlatformIdleState

A pointer to an <a href="..\pepfx\nc-pepfx-pofxcallbackupdateplatformidlestate.md">UpdatePlatformIdleState</a> routine. PoFx sets the value of this member. The <b>UpdatePlatformIdleState</b> routine is implemented by PoFx. The PEP calls this routine to update the properties of the specified platform idle state.


### -field RequestCommon

A pointer to an <a href="..\pepfx\nc-pepfx-pofxcallbackrequestcommon.md">RequestCommon</a> routine. PoFx sets the value of this member. The <b>RequestCommon</b> routine is implemented by PoFx. The PEP calls this routine to perform a processing operation that is specified by a request ID.


## -remarks
The <b>KernelInformation</b> parameter to the <a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a> or <a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a> routine is a pointer to a <b>PEP_KERNEL_INFORMATION</b> structure. The PEP allocates this structure and sets the values of the <b>Version</b> and <b>Size</b> members of this structure before calling <b>PoFxRegisterPlugin</b> or <b>PoFxRegisterPluginEx</b>. During the call to this routine, PoFx fills in the remaining members of the structure.


## -see-also
<dl>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md">EnumerateUnmaskedInterrupts</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackplatformidleveto.md">PlatformIdleVeto</a>
</dt>
<dt>
<a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a>
</dt>
<dt>
<a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackprocessorhalt.md">ProcessorHalt</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackprocessoridleveto.md">ProcessorIdleVeto</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackrequestcommon.md">RequestCommon</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackrequestinterrupt.md">RequestInterrupt</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackrequestworker.md">RequestWorker</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackcriticalresource.md">TransitionCriticalResource</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackupdateplatformidlestate.md">UpdatePlatformIdleState</a>
</dt>
<dt>
<a href="..\pepfx\nc-pepfx-pofxcallbackupdateprocessoridlestate.md">UpdateProcessorIdleState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_KERNEL_INFORMATION_STRUCT_V3 structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

