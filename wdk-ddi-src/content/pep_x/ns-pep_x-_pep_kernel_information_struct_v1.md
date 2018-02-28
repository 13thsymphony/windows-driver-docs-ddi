---
UID: NS:pep_x._PEP_KERNEL_INFORMATION_STRUCT_V1
title: "_PEP_KERNEL_INFORMATION_STRUCT_V1"
author: windows-driver-content
description: The PEP_KERNEL_INFORMATION structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows power management framework (PoFx).
old-location: kernel\pep_kernel_information.htm
old-project: kernel
ms.assetid: 4FBBEF08-3BDA-43B2-A05B-B6BFC2787FC6
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_KERNEL_INFORMATION, *PPEP_KERNEL_INFORMATION_STRUCT_V1, PEP_KERNEL_INFORMATION, PEP_KERNEL_INFORMATION structure pointer [Kernel-Mode Driver Architecture], PEP_KERNEL_INFORMATION_STRUCT_V1, PEP_KERNEL_INFORMATION_STRUCT_V1 structure [Kernel-Mode Driver Architecture], PPEP_KERNEL_INFORMATION_STRUCT_V1, PPEP_KERNEL_INFORMATION_STRUCT_V1 structure pointer [Kernel-Mode Driver Architecture], _PEP_KERNEL_INFORMATION_STRUCT_V1, kernel.pep_kernel_information, pep_x/PEP_KERNEL_INFORMATION, pep_x/PEP_KERNEL_INFORMATION_STRUCT_V1, pep_x/PPEP_KERNEL_INFORMATION_STRUCT_V1"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pep_x.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pep_x.h
api_name:
-	PEP_KERNEL_INFORMATION_STRUCT_V1
product: Windows
targetos: Windows
req.typenames: PEP_KERNEL_INFORMATION_STRUCT_V1, *PPEP_KERNEL_INFORMATION_STRUCT_V1
---

# _PEP_KERNEL_INFORMATION_STRUCT_V1 structure
The <b>PEP_KERNEL_INFORMATION</b> structure specifies the interface that the power extension plug-in (PEP) uses to request services from the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx).

## Syntax
````
typedef struct _PEP_KERNEL_INFORMATION_STRUCT_V1 {
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
  PPOFXCALLBACKCOMPLETEWORK                CompleteWork;
  PPOFXCALLBACKREQUESTCOMMON               RequestCommon;
} PEP_KERNEL_INFORMATION_STRUCT_V1, *PPEP_KERNEL_INFORMATION_STRUCT_V1, *PEP_KERNEL_INFORMATION;
````

## Members


`EnumerateUnmaskedInterrupts`

A pointer to an <a href="..\pepfx\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md">EnumerateUnmaskedInterrupts</a> routine. PoFx sets the value of this member. The <b>EnumerateUnmaskedInterrupts</b> routine is implemented by PoFx. The PEP calls this routine to request information about the unmasked interrupts.

`Plugin`

The handle assigned to the PEP's registration with PoFx. PoFx sets the value of this member. The PEP uses this handle in calls to the <a href="..\pepfx\nc-pepfx-pofxcallbackrequestworker.md">RequestWorker</a> routine.

`ProcessorHalt`

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackprocessorhalt.md">ProcessorHalt</a> routine. PoFx sets the value of this member. The <b>ProcessorHalt</b> routine is implemented by PoFx. The PEP calls this routine to prepare the current processor to enter the halted state.

`RequestInterrupt`

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackrequestinterrupt.md">RequestInterrupt</a> routine. PoFx sets the value of this member. The <b>RequestInterrupt</b> routine is implemented by PoFx. The PEP calls this routine to replay an edge-triggered interrupt that might have been lost after the hardware platform entered a low-power system state.

`RequestWorker`

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackrequestworker.md">RequestWorker</a> routine. PoFx sets the value of this member. The <b>RequestWorker</b> routine is implemented by PoFx. The PEP calls this routine to request the use of a worker thread from the operating system.

`Size`

The size, in bytes, of this structure. Set this member to <b>sizeof</b>(<b>PEP_KERNEL_INFORMATION</b>).

`TransitionCriticalResource`

A pointer to a <a href="..\pepfx\nc-pepfx-pofxcallbackcriticalresource.md">TransitionCriticalResource</a> routine. PoFx sets the value of this member. The <b>TransitionCriticalResource</b> routine is implemented by PoFx. The PEP calls this routine to transition critical system resources to the idle condition.

`Version`

The current version number for this structure. Set this member to PEP_KERNEL_INFORMATION_VERSION.

## Remarks
The <b>KernelInformation</b> parameter to the <a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a> or <a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a> routine is a pointer to a <b>PEP_KERNEL_INFORMATION</b> structure. The PEP allocates this structure and sets the values of the <b>Version</b> and <b>Size</b> members of this structure before calling <b>PoFxRegisterPlugin</b> or <b>PoFxRegisterPluginEx</b>. During the call to this routine, PoFx fills in the remaining members of the structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 10. Supported starting with Windows 10. |
| **Header** | pep_x.h |

## See Also

<a href="..\pepfx\nc-pepfx-pofxcallbackprocessoridleveto.md">ProcessorIdleVeto</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackupdateplatformidlestate.md">UpdatePlatformIdleState</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186629">CompleteWork</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackupdateprocessoridlestate.md">UpdateProcessorIdleState</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackenumerateunmaskedinterrupts.md">EnumerateUnmaskedInterrupts</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackprocessorhalt.md">ProcessorHalt</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackrequestinterrupt.md">RequestInterrupt</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackplatformidleveto.md">PlatformIdleVeto</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackcriticalresource.md">TransitionCriticalResource</a>



<a href="..\pepfx\nf-pepfx-pofxregisterplugin.md">PoFxRegisterPlugin</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackrequestcommon.md">RequestCommon</a>



<a href="..\pepfx\nf-pepfx-pofxregisterpluginex.md">PoFxRegisterPluginEx</a>



<a href="..\pepfx\nc-pepfx-pofxcallbackrequestworker.md">RequestWorker</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_KERNEL_INFORMATION_STRUCT_V1 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>