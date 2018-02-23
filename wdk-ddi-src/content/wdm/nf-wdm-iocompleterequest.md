---
UID: NF:wdm.IoCompleteRequest
title: IoCompleteRequest macro
author: windows-driver-content
description: The IoCompleteRequest routine indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager.
old-location: kernel\iocompleterequest.htm
old-project: kernel
ms.assetid: 59252b09-00ee-4a39-9849-5ce840ee16a7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: k104_79ea2b93-3ce8-46eb-990b-ca3e56d3e3a8.xml, wdm/IoCompleteRequest, IoCompleteRequest routine [Kernel-Mode Driver Architecture], kernel.iocompleterequest, IoCompleteRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: CompleteRequest, CompleteRequestStatusCheck, DoubleCompletion, IoAllocateComplete, IoBuildFsdComplete, IoSetCompletionExCompleteIrp, IrpProcessingComplete, MarkIrpPending, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, SpinLockSafe, WmiComplete, HwStorPortProhibitedDDIs, SpinLockSafe(storport)
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	IoCompleteRequest
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# IoCompleteRequest function
The <b>IoCompleteRequest</b> routine indicates that the caller has completed all processing for a given I/O request and is returning the given IRP to the I/O manager.

## Syntax

````
VOID IoCompleteRequest(
  _In_ PIRP  Irp,
  _In_ CCHAR PriorityBoost
);
````

## Parameters

`a`

TBD

`b`

TBD


## Return Value

None

## Remarks

When a driver has finished all processing for a given IRP, it calls <b>IoCompleteRequest</b>. The I/O manager checks the IRP to determine whether any higher-level drivers have set up an <a href="..\wdm\nc-wdm-io_completion_routine.md">IoCompletion</a> routine for the IRP. If so, each <i>IoCompletion</i> routine is called, in turn, until every layered driver in the chain has completed the IRP.

When all drivers have completed a given IRP, the I/O manager returns status to the original requester of the operation. Note that a higher-level driver that sets up a driver-created IRP must supply an <i>IoCompletion</i> routine to release the IRP it created.

Never call <b>IoCompleteRequest</b> while holding a spin lock. Attempting to complete an IRP while holding a spin lock can cause deadlocks.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | CompleteRequest, CompleteRequestStatusCheck, DoubleCompletion, IoAllocateComplete, IoBuildFsdComplete, IoSetCompletionExCompleteIrp, IrpProcessingComplete, MarkIrpPending, PendedCompletedRequest, PendedCompletedRequest2, PendedCompletedRequest3, PendedCompletedRequestEx, PnpIrpCompletion, SpinLockSafe, WmiComplete, HwStorPortProhibitedDDIs, SpinLockSafe(storport) |

## See Also

<a href="..\wdm\nf-wdm-iosetcompletionroutine.md">IoSetCompletionRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCompleteRequest routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>