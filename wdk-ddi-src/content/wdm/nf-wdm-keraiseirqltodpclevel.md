---
UID: NF:wdm.KeRaiseIrqlToDpcLevel
title: KeRaiseIrqlToDpcLevel function
author: windows-driver-content
description: The KeRaiseIrqlToDpcLevel routine raises the hardware priority to IRQL = DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor.
old-location: kernel\keraiseirqltodpclevel.htm
old-project: kernel
ms.assetid: ac82e003-ec05-4b8b-a4fb-64498fb17f9b
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: KeRaiseIrqlToDpcLevel, KeRaiseIrqlToDpcLevel routine [Kernel-Mode Driver Architecture], k105_64c33a5b-8efa-4d97-9569-2ea68a227d17.xml, kernel.keraiseirqltodpclevel, wdm/KeRaiseIrqlToDpcLevel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h
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
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Hal.lib
-	Hal.dll
api_name:
-	KeRaiseIrqlToDpcLevel
product: Windows
targetos: Windows
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---


# KeRaiseIrqlToDpcLevel function
The <b>KeRaiseIrqlToDpcLevel</b> routine raises the hardware priority to IRQL = DISPATCH_LEVEL, thereby masking off interrupts of equivalent or lower IRQL on the current processor.

## Syntax

````
KIRQL KeRaiseIrqlToDpcLevel(void);
````

## Parameters

This function has no parameters.

## Return Value

<b>KeRaiseIrqlToDpcLevel</b> returns the IRQL at which the call occurred.

## Remarks

Any caller of <b>KeRaiseIrqlToDpcLevel</b> should save the returned IRQL value. Every such caller must restore the original IRQL as quickly as possible by passing this returned IRQL in a subsequent call to <a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>.

Callers of <b>KeRaiseIrqlToDpcLevel</b> must be running at IRQL &lt;= DISPATCH_LEVEL. Otherwise, a call to this routine causes a bug check.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 2000.  |
| **Target Platform** | Universal |
| **Header** | wdm.h (include Wdm.h, Ntddk.h) |
| **Library** | Hal.lib |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |
| **DDI compliance rules** | HwStorPortProhibitedDDIs |

## See Also

<a href="..\wdm\nf-wdm-kegetcurrentirql.md">KeGetCurrentIrql</a>



<a href="..\wdm\nf-wdm-keraiseirql.md">KeRaiseIrql</a>



<a href="..\wdm\nf-wdm-kelowerirql.md">KeLowerIrql</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20KeRaiseIrqlToDpcLevel routine%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>