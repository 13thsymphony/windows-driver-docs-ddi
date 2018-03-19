---
UID: NF:wdm.RtlSetBit
title: RtlSetBit function
author: windows-driver-content
description: The RtlSetBit routine sets the specified bit in a bitmap to one.
old-location: kernel\rtlsetbit.htm
old-project: kernel
ms.assetid: 6e78da3d-7a37-41f9-bfa6-db2e83581769
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlSetBit, RtlSetBit routine [Kernel-Mode Driver Architecture], k109_44d68cd0-b91e-4a4e-8f4f-c40e25b768b9.xml, kernel.rtlsetbit, wdm/RtlSetBit
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
req.irql: "<= APC_LEVEL (See Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	NtosKrnl.exe
api_name:
-	RtlSetBit
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlSetBit function
The <b>RtlSetBit</b> routine sets the specified bit in a bitmap to one.

## Syntax

````
VOID RtlSetBit(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       BitNumber
);
````

## Parameters

`BitMapHeader`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine.

`BitNumber`

Specifies the zero-based index of the bit within the bitmap. The routine sets this bit to one.


## Return Value

None

## Remarks

Callers of <b>RtlSetBit</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlSetBit</b> can be called at any IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows XP and later versions of Windows.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.lib |
| **DLL** | NtosKrnl.exe |
| **IRQL** | "<= APC_LEVEL (See Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>