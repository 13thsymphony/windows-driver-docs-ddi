---
UID: NF:wdm.KeRaiseIrql
title: KeRaiseIrql macro
author: windows-driver-content
description: The KeRaiseIrql routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
old-location: kernel\keraiseirql.htm
old-project: kernel
ms.assetid: ee340d85-5a66-4773-b325-831257e9bfd8
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: KeRaiseIrql, KeRaiseIrql routine [Kernel-Mode Driver Architecture], k105_66b09c47-8f95-41ee-8432-5784f306ad62.xml, kernel.keraiseirql, wdm/KeRaiseIrql
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: IrqlKeRaiseLower, IrqlKeRaiseLower2, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Hal.lib
req.dll: 
req.irql: Any level (see Remarks section)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	KeRaiseIrql
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeRaiseIrql function
The <b>KeRaiseIrql</b> routine raises the hardware priority to the specified IRQL value, thereby masking off interrupts of equivalent or lower IRQL on the current processor.

## Syntax

````
VOID KeRaiseIrql(
  _In_  KIRQL  NewIrql,
  _Out_ PKIRQL OldIrql
);
````

## Parameters

`a`

TBD

`b`

TBD


## Return Value

None

## Remarks

If the new IRQL is less than the current IRQL, a bug check occurs. Otherwise, the current IRQL is set to the specified value.

Callers of this routine can be running at any IRQL. Any caller should restore the original IRQL with <a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a> as soon as possible.

A call to <b>KeLowerIrql</b> is valid if it specifies <i>NewIrql</i> &lt;= <i>CurrentIrql</i>. A call to <b>KeRaiseIrql</b> is valid if the caller specifies <i>NewIrql</i> &gt;= <i>CurrentIrql</i>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** | Hal.lib |
| **IRQL** | Any level (see Remarks section) |
| **DDI compliance rules** | IrqlKeRaiseLower, IrqlKeRaiseLower2, HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>



<a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a>