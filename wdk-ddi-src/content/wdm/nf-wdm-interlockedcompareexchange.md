---
UID : NF:wdm.InterlockedCompareExchange
title : InterlockedCompareExchange function
author : windows-driver-content
description : The InterlockedCompareExchange routine performs an atomic operation that compares the input value pointed to by Destination with the value of Comparand.
old-location : kernel\interlockedcompareexchange.htm
old-project : kernel
ms.assetid : 925a5481-d626-4824-8cbe-4fc2a0a6ad92
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : InterlockedCompareExchange
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Universal
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : InterlockedCompareExchange
req.alt-loc : OneCoreUAP.lib,OneCoreUAP.dll,API-MS-Win-Core-Interlocked-l1-1-0.dll,API-MS-Win-Core-Interlocked-l1-2-0.dll,KernelBase.dll,MinKernelBase.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : OneCoreUAP.lib on Windows 10
req.dll : 
req.irql : Any level
req.typenames : WORK_QUEUE_TYPE
req.product : Windows 10 or later.
---


# InterlockedCompareExchange function
The <b>InterlockedCompareExchange</b> routine performs an atomic operation that compares the input value pointed to by <i>Destination</i> with the value of <i>Comparand</i>.

## Syntax

````
LONG InterlockedCompareExchange(
  _Inout_ LONG volatile *Destination ,
  _In_    LONG          Exchange ,
  _In_    LONG          Comparand
);
````

## Parameters

`Destination`

A pointer to the input value that is compared with the value of <i>Comparand</i>.

`ExChange`



`Comperand`




## Return Value

<b>InterlockedCompareExchange</b> returns the original value of *<i>Destination</i>.

## Remarks

If <i>Comparand</i> is equal to *<i>Destination</i>, then *<i>Destination</i> is set to equal <i>Exchange</i>. Otherwise, *<i>Destination</i> is unchanged.

<b>InterlockedCompareExchange</b> provides a fast, atomic way to synchronize the testing and updating of a variable that is shared by multiple threads. If the input value pointed to by <i>Destination</i> equals the value of <i>Comparand</i>, the output value of <i>Destination</i> is set to the value of <i>Exchange</i>. 

<b>InterlockedCompareExchange</b> is designed for speed and, typically, is implemented inline by a compiler. <b>InterlockedCompareExchange </b>is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. It does not use a spin lock and can be safely used on pageable data. 

Interlocked operations cannot be used on non-cached memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | Any level |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wdm\nf-wdm-exinterlockedcompareexchange64.md">ExInterlockedCompareExchange64</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-interlockedcompareexchangepointer.md">InterlockedCompareExchangePointer</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-interlockeddecrement.md">InterlockedDecrement</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-interlockedexchange.md">InterlockedExchange</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-interlockedexchangepointer.md">InterlockedExchangePointer</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-interlockedincrement.md">InterlockedIncrement</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20InterlockedCompareExchange routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>