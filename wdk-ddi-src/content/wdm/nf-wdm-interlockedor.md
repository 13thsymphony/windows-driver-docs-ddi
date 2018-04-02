---
UID: NF:wdm.InterlockedOr
title: InterlockedOr function
author: windows-driver-content
description: The InterlockedOr routine atomically computes a bitwise OR operation.
old-location: kernel\interlockedor.htm
old-project: kernel
ms.assetid: 1f66d3ed-7215-4fb5-87df-4489c3cd03c6
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: InterlockedOr, InterlockedOr routine [Kernel-Mode Driver Architecture], k102_05d8ca48-ab6f-46ae-b026-cb2aaf6f37aa.xml, kernel.interlockedor, wdm/InterlockedOr
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
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
-	InterlockedOr
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# InterlockedOr function
The <b>InterlockedOr</b> routine atomically computes a bitwise OR operation.

## Syntax

```
LONG InterlockedOr(
  _Interlocked_operand_ LONG *Destination,
  LONG                       Value
);
```

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
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h, Miniport.h) |
| **IRQL** | Any level |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff547844">InterlockedAnd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547933">InterlockedXor</a>