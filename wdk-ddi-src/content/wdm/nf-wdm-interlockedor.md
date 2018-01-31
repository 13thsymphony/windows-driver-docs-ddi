---
UID : NF:wdm.InterlockedOr
title : InterlockedOr function
author : windows-driver-content
description : The InterlockedOr routine atomically computes a bitwise OR operation.
old-location : kernel\interlockedor.htm
old-project : kernel
ms.assetid : 1f66d3ed-7215-4fb5-87df-4489c3cd03c6
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : InterlockedOr, k102_05d8ca48-ab6f-46ae-b026-cb2aaf6f37aa.xml, InterlockedOr routine [Kernel-Mode Driver Architecture], wdm/InterlockedOr, kernel.interlockedor
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.lib : NtosKrnl.exe
req.dll : 
req.irql : Any level
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# InterlockedOr function
The <b>InterlockedOr</b> routine atomically computes a bitwise OR operation.

## Syntax

````
LONG InterlockedOr(
  _Inout_ LONG volatile *Destination,
  _In_    LONG          Value
);
````

## Parameters

`Destination`

A pointer to the variable to be ORed with <i>Value</i>. The result of the operation is stored in the variable.

`Value`

Specifies the value to be ORed with the variable that is pointed to by <i>Destination</i>.


## Return Value

<b>InterlockedOr</b> returns the original value stored in the variable pointed to by <i>Destination</i>.

## Remarks

<b>InterlockedOr</b> atomically computes <b>*</b><i>Destination</i><b>|=</b><i>Value</i>. 

Interlocked operations cannot be used on non-cached memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<a href="..\wdm\nf-wdm-interlockedxor.md">InterlockedXor</a>

<a href="..\wdm\nf-wdm-interlockedand.md">InterlockedAnd</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedOr routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>