---
UID: NF:wdm.KeGetCurrentIrql
title: KeGetCurrentIrql function
author: windows-driver-content
description: The KeGetCurrentIrql routine returns the current IRQL.
old-location: kernel\kegetcurrentirql.htm
old-project: kernel
ms.assetid: 63c33017-d827-4a8f-bb6f-fd13a2528e0c
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: KeGetCurrentIrql, KeGetCurrentIrql routine [Kernel-Mode Driver Architecture], k105_04c845e8-a239-4400-8a5f-15996754494a.xml, kernel.kegetcurrentirql, wdm/KeGetCurrentIrql
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	KeGetCurrentIrql
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeGetCurrentIrql function
The <b>KeGetCurrentIrql</b> routine returns the current IRQL.

## Syntax

```
_IRQL_saves_ NTHALAPI KIRQL KeGetCurrentIrql(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>KeGetCurrentIrql</b> returns the current IRQL.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551921">KeAcquireSpinLockAtDpcLevel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552968">KeLowerIrql</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff553079">KeRaiseIrql</a>