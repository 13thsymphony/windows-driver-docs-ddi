---
UID: NF:wdm.ExFreePool
title: ExFreePool function
author: windows-driver-content
description: The ExFreePool routine deallocates a block of pool memory.
old-location: kernel\exfreepool.htm
old-project: kernel
ms.assetid: c26f9b28-396d-40de-bdc3-287fc3ac4113
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: ExFreePool, ExFreePool routine [Kernel-Mode Driver Architecture], k102_134b475a-f669-4f1e-8836-f41945d7230c.xml, kernel.exfreepool, wdm/ExFreePool
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
req.ddi-compliance: DoubleExFreePool
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	ExFreePool
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# ExFreePool function
The <b>ExFreePool</b> routine deallocates a block of pool memory.

## Syntax

```
NTKERNELAPI VOID ExFreePool(
  __drv_freesMem(Mem)PVOID P
);
```

## Parameters

`P`




## Return Value

None

## Remarks

This routine releases memory allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff544501">ExAllocatePool</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544506">ExAllocatePoolWithQuota</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>. The memory block must not be accessed after it is freed.

Drivers can also use the <b>ExFreePoolWithTag</b> routine to free buffers allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>.

Callers of <b>ExFreePool</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must have specified a <b>NonPaged</b><i>Xxx</i><i>PoolType</i> when the memory was allocated. Otherwise, the caller must be running at IRQL &lt;= APC_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |
| **DDI compliance rules** | DoubleExFreePool |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544501">ExAllocatePool</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544506">ExAllocatePoolWithQuota</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544513">ExAllocatePoolWithQuotaTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544593">ExFreePoolWithTag</a>