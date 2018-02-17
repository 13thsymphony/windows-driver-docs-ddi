---
UID: NF:wdm.KeInsertQueueDpc
title: KeInsertQueueDpc function
author: windows-driver-content
description: The KeInsertQueueDpc routine queues a DPC for execution.
old-location: kernel\keinsertqueuedpc.htm
old-project: kernel
ms.assetid: f1fc6880-23d1-4154-9305-4a918efd4a1d
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.keinsertqueuedpc, wdm/KeInsertQueueDpc, k105_7f821e29-508f-4216-92db-a2e18c21d17c.xml, KeInsertQueueDpc routine [Kernel-Mode Driver Architecture], KeInsertQueueDpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: MarkingQueuedIrps, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	KeInsertQueueDpc
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeInsertQueueDpc function
The <b>KeInsertQueueDpc</b> routine queues a DPC for execution.

## Syntax

````
BOOLEAN KeInsertQueueDpc(
  _Inout_  PRKDPC Dpc,
  _In_opt_ PVOID  SystemArgument1,
  _In_opt_ PVOID  SystemArgument2
);
````

## Parameters

`Dpc`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure for the DPC object. This structure must have been initialized by either <a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a> or <a href="..\wdm\nf-wdm-keinitializethreadeddpc.md">KeInitializeThreadedDpc</a>.

`SystemArgument1`

Specifies driver-determined context data. This value is passed as the <i>SystemArgument1</i> parameter to the DPC object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine.

`SystemArgument2`

Specifies driver-determined context data. This value is passed as the <i>SystemArgument2</i> parameter to the DPC object's <a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine.


## Return Value

If the specified DPC object is not currently in a DPC queue, <b>KeInsertQueueDpc</b> queues the DPC and returns <b>TRUE</b>.

## Remarks

If the specified DPC object has already been queued, no operation is performed except to return <b>FALSE</b>. Otherwise, the DPC object is inserted in a DPC queue. For more information about DPC queues, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff558754">Organization of DPC Queues</a>.

Note that a particular DPC object and the function that it represents can each be queued for execution only once at any particular time.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |
| **DDI compliance rules** | MarkingQueuedIrps, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-keremovequeuedpc.md">KeRemoveQueueDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542972">CustomDpc</a>



<a href="..\wdm\nf-wdm-keinitializedpc.md">KeInitializeDpc</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeInsertQueueDpc routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>