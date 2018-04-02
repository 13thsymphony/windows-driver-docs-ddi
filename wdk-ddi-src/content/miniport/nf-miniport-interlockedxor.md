---
UID: NF:miniport.InterlockedXor
title: InterlockedXor function
author: windows-driver-content
description: The InterlockedOr routine atomically computes a bitwise exclusive OR operation.
old-location: kernel\interlockedxor.htm
old-project: kernel
ms.assetid: 3ddf62f1-ce5d-4d55-9964-8d1786ac2997
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: InterlockedXor, InterlockedXor routine [Kernel-Mode Driver Architecture], k102_7b4b6df0-2179-4a6a-941d-5aaa95609cd8.xml, kernel.interlockedxor, wdm/InterlockedXor
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: miniport.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h, Miniport.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
-	InterlockedXor
product: Windows
targetos: Windows
req.typenames: MEMORY_CACHING_TYPE
---


# InterlockedXor function
The <b>InterlockedOr</b> routine atomically computes a bitwise exclusive OR operation.

## Syntax

```
LONG InterlockedXor(
  _Interlocked_operand_ LONG *Destination,
  LONG                       Value
);
```

## Parameters

`Destination`

A pointer to the variable to be exclusive ORed with <i>Value</i>. The result of the operation is stored in the variable.

`Value`

Specifies the value to be exclusive ORed with the variable that is pointed to by <i>Destination</i>.


## Return Value

<b>InterlockedXor</b> returns the original value stored in the variable pointed to by <i>Destination</i>.

## Remarks

<b>InterlockedXor</b> atomically computes <b>*</b><i>Destination</i><b>^=</b><i>Value</i>. 

Interlocked operations cannot be used on non-cached memory.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | miniport.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547844">InterlockedAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547928">InterlockedOr</a>