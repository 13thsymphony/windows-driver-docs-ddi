---
UID: NF:miniport.InterlockedExchangePointer
title: InterlockedExchangePointer function
author: windows-driver-content
description: The InterlockedExchangePointer routine performs an atomic operation that sets a pointer to a new value.
old-location: kernel\interlockedexchangepointer.htm
old-project: kernel
ms.assetid: 8c39a62d-0c05-4d26-b104-90c436e821cb
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: InterlockedExchangePointer, InterlockedExchangePointer routine [Kernel-Mode Driver Architecture], k102_4959af35-65d8-4768-94f7-a2dad0a2db46.xml, kernel.interlockedexchangepointer, wdm/InterlockedExchangePointer
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
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
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wdm.h
api_name:
-	InterlockedExchangePointer
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# InterlockedExchangePointer function
The <b>InterlockedExchangePointer</b> routine performs an atomic operation that sets a pointer to a new value.

## Syntax

```
PVOID InterlockedExchangePointer(
  _Interlocked_operand_ PVOID *Target,
  PVOID                       Value
);
```

## Parameters

`Target`

A pointer to a PVOID value. The routine sets (*<i>Target</i>) to <i>Value</i>.

`Value`

Specifies the PVOID value to set (*<i>Target</i>) to.


## Return Value

<b>InterlockedExchangePointer</b> returns the original value of the pointer at *<i>Target</i> (that is, the value of this pointer at entry to the routine).

## Remarks

<b>InterlockedExchangePointer</b> provides a fast, atomic way to synchronize updating a pointer variable that is shared by multiple threads.

<b>InterlockedExchangePointer</b> is designed for speed and, typically, is implemented inline by a compiler. <b>InterlockedExchangePointer</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls. It does not use a spin lock and can be safely used on pageable data. 

The <i>Target</i> parameter should be aligned on either a 32-bit or 64-bit boundary, depending on the system type, for better performance.

A call to <b>InterlockedExchangePointer</b> is atomic only with respect to other <b>Interlocked<i>Xxx</i></b> calls.

Interlocked operations cannot be used on non-cached memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Desktop |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547853">InterlockedCompareExchange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547863">InterlockedCompareExchangePointer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547892">InterlockedExchange</a>