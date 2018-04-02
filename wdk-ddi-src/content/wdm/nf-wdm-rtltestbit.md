---
UID: NF:wdm.RtlTestBit
title: RtlTestBit function
author: windows-driver-content
description: The RtlTestBit routine returns the value of a bit in a bitmap.
old-location: kernel\rtltestbit.htm
old-project: kernel
ms.assetid: 52f892a8-e82d-465d-aef5-630f5e971e8f
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: RtlTestBit, RtlTestBit routine [Kernel-Mode Driver Architecture], k109_552764bc-c69d-4039-8284-8cc8f41dc16a.xml, kernel.rtltestbit, wdm/RtlTestBit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows XP and later versions of Windows.
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
req.irql: "<= APC_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlTestBit
product:
- Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlTestBit function
The <b>RtlTestBit</b> routine returns the value of a bit in a bitmap.

## Syntax

```
NTSYSAPI BOOLEAN RtlTestBit(
  PRTL_BITMAP BitMapHeader,
  ULONG       BitNumber
);
```

## Parameters

`BitMapHeader`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a> routine.

`BitNumber`

Specifies the zero-based index of the bit within the bitmap. The routine returns the value of this bit.


## Return Value

<b>RtlTestBit</b> returns the value of the bit that the <i>BitNumber</i> parameter points to.

## Remarks

Callers of <b>RtlTestBit</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlTestBit</b> can be called at any IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL (see Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561925">RtlInitializeBitMap</a>