---
UID : NF:wdm.InterlockedCompareExchangePointer
title : InterlockedCompareExchangePointer function
author : windows-driver-content
description : The InterlockedCompareExchangePointer routine performs an atomic operation that compares the input pointer value pointed to by Destination with the pointer value Comparand.
old-location : kernel\interlockedcompareexchangepointer.htm
old-project : kernel
ms.assetid : 3b96076f-a7f7-4705-bbee-595ee4d9f789
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.interlockedcompareexchangepointer, InterlockedCompareExchangePointer, wdm/InterlockedCompareExchangePointer, k102_ffaadb46-ece2-40fb-9e87-1c7ea3af275e.xml, InterlockedCompareExchangePointer routine [Kernel-Mode Driver Architecture]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
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


# InterlockedCompareExchangePointer function
The <b>InterlockedCompareExchangePointer</b> routine performs an atomic operation that compares the input pointer value pointed to by <i>Destination</i> with the pointer value <i>Comparand</i>.

## Syntax

````
PVOID InterlockedCompareExchangePointer(
  _Inout_ PVOID *Destination ,
  _In_    PVOID Exchange ,
  _In_    PVOID Comparand
);
````

## Parameters

`Destination`

A pointer to a PVOID value. If (*<i>Destination</i>) = <i>Comparand</i>, then the routine sets (*<i>Destination</i>) to <i>Exchange</i>.

`Exchange`

Specifies the PVOID value to set (*<i>Destination</i>) to.

`Comperand`

TBD


## Return Value

<b>InterlockedCompareExchangePointer</b> returns the original value of the pointer at *<i>Destination</i> (that is, the value of this pointer at entry to the routine).

## Remarks

If <i>Comparand</i> is equal to *<i>Destination</i>, then *<i>Destination</i> is set to equal <i>Exchange</i>. Otherwise, *<i>Destination</i> is unchanged.

<b>InterlockedCompareExchangePointer</b> provides a fast, atomic way to synchronize the testing and updating of a pointer variable that is shared by multiple threads. If the input value pointed to by <i>Destination</i> equals the value of <i>Comparand</i>, the value pointed to by <i>Destination</i> is set to the value of <i>Exchange</i>.

<b>InterlockedCompareExchangePointer</b> is designed for speed and, typically, is implemented inline by a compiler. <b>InterlockedCompareExchangePointer</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. It does not use a spin lock and can be safely used on pageable data.

The <b>InterlockedCompareExchangePointer</b> routine is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls.

Interlocked operations cannot be used on non-cached memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000. Available starting with Windows 2000. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | Any level |

## See Also

<a href="..\wdm\nf-wdm-interlockedexchange.md">InterlockedExchange</a>

<a href="..\wdm\nf-wdm-interlockedcompareexchange.md">InterlockedCompareExchange</a>

<a href="..\wdm\nf-wdm-interlockedexchangepointer.md">InterlockedExchangePointer</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedCompareExchangePointer routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>