---
UID: NF:wdm.RtlCheckBit
title: RtlCheckBit macro
author: windows-driver-content
description: The RtlCheckBit routine determines whether a particular bit in a given bitmap variable is clear or set.
old-location: kernel\rtlcheckbit.htm
old-project: kernel
ms.assetid: 2c9842de-a256-46ed-84b4-b8a595c01a62
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: RtlCheckBit, RtlCheckBit routine [Kernel-Mode Driver Architecture], k109_1f4676c1-d031-4a2c-8d74-afa9d3a0ed10.xml, kernel.rtlcheckbit, wdm/RtlCheckBit
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
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
req.lib: 
req.dll: 
req.irql: "<= APC_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	RtlCheckBit
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# RtlCheckBit function
The <b>RtlCheckBit</b> routine determines whether a particular bit in a given bitmap variable is clear or set.

## Syntax

````
ULONG RtlCheckBit(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       BitPosition
);
````

## Parameters

`BMH`

TBD

`BP`

TBD


## Return Value

None

## Remarks

Callers of <b>RtlCheckBit</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlCheckBit</b> can be called at any IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | "<= APC_LEVEL (see Remarks section)" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>



<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>



<a href="..\wdm\nf-wdm-rtlarebitsset.md">RtlAreBitsSet</a>



<a href="..\wdm\nf-wdm-rtlarebitsclear.md">RtlAreBitsClear</a>



<a href="..\wdm\nf-wdm-rtlnumberofclearbits.md">RtlNumberOfClearBits</a>



<a href="..\wdm\nf-wdm-rtlnumberofsetbits.md">RtlNumberOfSetBits</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlCheckBit routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>