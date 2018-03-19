---
UID: NF:wdm.RtlNumberOfSetBits
title: RtlNumberOfSetBits function
author: windows-driver-content
description: The RtlNumberOfSetBits routine returns a count of the set bits in a given bitmap variable.
old-location: kernel\rtlnumberofsetbits.htm
old-project: kernel
ms.assetid: 6208f750-4871-43b9-b848-011180d39fd8
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlNumberOfSetBits, RtlNumberOfSetBits routine [Kernel-Mode Driver Architecture], k109_b8b2c3f8-3ec3-4690-90bb-e5b120b5b062.xml, kernel.rtlnumberofsetbits, wdm/RtlNumberOfSetBits
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode); Ntdll.dll (user mode)
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
-	Ntdll.dll
api_name:
-	RtlNumberOfSetBits
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlNumberOfSetBits function
The <b>RtlNumberOfSetBits</b> routine returns a count of the set bits in a given bitmap variable.

## Syntax

````
ULONG RtlNumberOfSetBits(
  _In_ PRTL_BITMAP BitMapHeader
);
````

## Parameters

`BitMapHeader`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine.


## Return Value

<b>RtlNumberOfSetBits</b> returns a count of the bits that are currently set.

## Remarks

Callers of <b>RtlNumberOfSetBits</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlNumberOfSetBits</b> can be called at any IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe (kernel mode); Ntdll.dll (user mode) |
| **IRQL** | "<= APC_LEVEL (See Remarks section)" |

## See Also

<a href="..\wdm\nf-wdm-rtlnumberofclearbits.md">RtlNumberOfClearBits</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="..\wdm\nf-wdm-rtlfindsetbits.md">RtlFindSetBits</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>