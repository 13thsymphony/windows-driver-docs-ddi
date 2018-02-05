---
UID : NF:wdm.RtlEqualMemory
title : RtlEqualMemory macro
author : windows-driver-content
description : The RtlEqualMemory routine compares two blocks of memory to determine whether the specified number of bytes are identical.
old-location : kernel\rtlequalmemory.htm
old-project : kernel
ms.assetid : 43695fa9-32e1-4bd5-b146-88d6d03fe9fb
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : RtlEqualMemory routine [Kernel-Mode Driver Architecture], RtlEqualMemory, wdm/RtlEqualMemory, k109_a75dfbc8-12af-4f95-9ba0-b7752b796e55.xml, kernel.rtlequalmemory
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : macro
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 2000.
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
req.lib : wdm.h
req.dll : 
req.irql : Any level (See Remarks section)
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# RtlEqualMemory function
The <b>RtlEqualMemory</b> routine compares two blocks of memory to determine whether the specified number of bytes are identical.

## Syntax

````
LOGICAL RtlEqualMemory(
  _In_ const VOID   *Source1,
  _In_ const VOID   *Source2,
  _In_       SIZE_T Length
);
````

## Parameters

`Destination`

TBD

`Source`

TBD

`Length`

Specifies the number of bytes to be compared.


## Return Value

None

## Remarks

<b>RtlEqualMemory</b> begins the comparison with byte zero of each block.

Callers of <b>RtlEqualMemory</b> can be running at any IRQL if both blocks of memory are resident.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | wdm.h |
| **IRQL** | Any level (See Remarks section) |

## See Also

<a href="..\wdm\nf-wdm-rtlcomparememory.md">RtlCompareMemory</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20RtlEqualMemory routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>