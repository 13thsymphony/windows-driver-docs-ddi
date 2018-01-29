---
UID : NF:wdm.RtlTestBit
title : RtlTestBit function
author : windows-driver-content
description : The RtlTestBit routine returns the value of a bit in a bitmap.
old-location : kernel\rtltestbit.htm
old-project : kernel
ms.assetid : 52f892a8-e82d-465d-aef5-630f5e971e8f
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlTestBit, kernel.rtltestbit, wdm/RtlTestBit, k109_552764bc-c69d-4039-8284-8cc8f41dc16a.xml, RtlTestBit routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available in Windows XP and later versions of Windows.
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
req.irql : "<= APC_LEVEL (see Remarks section)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlTestBit function
The <b>RtlTestBit</b> routine returns the value of a bit in a bitmap.

## Syntax

````
BOOLEAN RtlTestBit(
  _In_ PRTL_BITMAP BitMapHeader,
  _In_ ULONG       BitNumber
);
````

## Parameters

`BitMapHeader`

Pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a> structure that describes the bitmap. This structure must have been initialized by the <a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a> routine.

`BitNumber`

Specifies the zero-based index of the bit within the bitmap. The routine returns the value of this bit.


## Return Value

<b>RtlTestBit</b> returns the value of the bit that the <i>BitNumber</i> parameter points to.

## Remarks

Callers of <b>RtlTestBit</b> must be running at IRQL &lt;= APC_LEVEL if the memory that contains the bitmap variable is pageable or the memory at <i>BitMapHeader</i> is pageable. Otherwise, <b>RtlTestBit</b> can be called at any IRQL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL (see Remarks section) |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-rtlinitializebitmap.md">RtlInitializeBitMap</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff563614">RTL_BITMAP</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlTestBit routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>