---
UID : NF:wdm.IoWithinStackLimits
title : IoWithinStackLimits function
author : windows-driver-content
description : The IoWithinStackLimits routine determines whether a region of memory is within the stack limit of the current thread.
old-location : kernel\iowithinstacklimits.htm
old-project : kernel
ms.assetid : af182cd5-23b5-4d5b-b3d4-ec65ec087d0b
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : k104_631648cb-6ba2-47b1-8745-e6314e17be30.xml, IoWithinStackLimits routine [Kernel-Mode Driver Architecture], wdm/IoWithinStackLimits, IoWithinStackLimits, kernel.iowithinstacklimits
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available on Windows Vista and later versions of the Windows operating system.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : NtosKrnl.lib
req.dll : NtosKrnl.exe
req.irql : <= APC_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# IoWithinStackLimits function
The <b>IoWithinStackLimits</b> routine determines whether a region of memory is within the stack limit of the current thread.

## Syntax

````
LOGICAL IoWithinStackLimits(
  _In_ ULONG_PTR RegionStart,
  _In_ SIZE_T    RegionSize
);
````

## Parameters

`RegionStart`

A pointer to the start of the region.

`RegionSize`

The size of the region.


## Return Value

<b>IoWithinStackLimits</b> returns <b>TRUE</b> is the current thread's stack contains the region completely and <b>FALSE</b> otherwise.

## Remarks

The <b>IoWithinStackLimits</b> routine considers all possible stack segments and the DPC stack, if necessary.
<div class="alert"><b>Note</b>    For drivers that use <a href="..\ntddk\nf-ntddk-keexpandkernelstackandcallout.md">KeExpandKernelStackAndCallout</a>, <b>IoWithinStackLimits</b> considers only the current thread.</div><div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-iogetstacklimits.md">IoGetStackLimits</a>

<a href="..\wdm\nf-wdm-iogetinitialstack.md">IoGetInitialStack</a>

<a href="..\wdm\nf-wdm-iogetremainingstacksize.md">IoGetRemainingStackSize</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoWithinStackLimits routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>