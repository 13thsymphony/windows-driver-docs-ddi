---
UID: NF:wdm.KeInitializeThreadedDpc
title: KeInitializeThreadedDpc function
author: windows-driver-content
description: The KeInitializeThreadedDpc routine initializes a threaded DPC object, and registers a CustomThreadedDpc routine for that object.
old-location: kernel\keinitializethreadeddpc.htm
old-project: kernel
ms.assetid: ee9124db-9d92-42e1-84fa-6d3eefeaeac5
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeInitializeThreadedDpc, KeInitializeThreadedDpc routine [Kernel-Mode Driver Architecture], k105_b5df057f-6d75-4a06-ac5f-d99340bdbb21.xml, kernel.keinitializethreadeddpc, wdm/KeInitializeThreadedDpc
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Vista and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	KeInitializeThreadedDpc
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeInitializeThreadedDpc function
The <b>KeInitializeThreadedDpc</b> routine initializes a threaded DPC object, and registers a <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine for that object.

## Syntax

````
VOID KeInitializeThreadedDpc(
  _Out_    PRKDPC             Dpc,
  _In_     PKDEFERRED_ROUTINE DeferredRoutine,
  _In_opt_ PVOID              DeferredContext
);
````

## Parameters

`Dpc`

Pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff551882">KDPC</a> structure that represents the DPC object to initialize. The caller must allocate storage for the structure from resident memory.

`DeferredRoutine`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a> routine to associate with the DPC.

`DeferredContext`

Specifies the value to pass as the <i>DeferredContext</i> parameter to <a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a>.


## Return Value

None

## Remarks

For more information about threaded DPCs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff564621">Threaded DPCs</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-keremovequeuedpc.md">KeRemoveQueueDpc</a>



<a href="..\wdm\nf-wdm-keinsertqueuedpc.md">KeInsertQueueDpc</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542976">CustomThreadedDpc</a>