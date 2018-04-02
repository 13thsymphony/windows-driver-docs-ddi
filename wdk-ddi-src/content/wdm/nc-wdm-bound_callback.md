---
UID: NC:wdm.BOUND_CALLBACK
title: BOUND_CALLBACK
author: windows-driver-content
description: The BoundCallback routine is executed whenever the system issues a bounds exception for a user-mode thread.
old-location: kernel\boundcallback.htm
old-project: kernel
ms.assetid: D9047BB2-2FCD-41DE-B1E1-DE89AAA40ED7
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: BOUND_CALLBACK, BoundCallback, BoundCallback routine [Kernel-Mode Driver Architecture], kernel.boundcallback, wdm/BoundCallback
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 10.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdm.h
api_name:
-	BoundCallback
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# BOUND_CALLBACK callback function
The <i>BoundCallback</i> routine is executed whenever the system issues a bounds exception for a user-mode thread.

## Syntax

```
BOUND_CALLBACK BoundCallback;

_IRQL_requires_same_ BOUND_CALLBACK_STATUS BoundCallback(

)
{...}
```

## Parameters

This function has no parameters.

## Return Value

A <a href="https://msdn.microsoft.com/library/windows/hardware/dn957854">BOUND_CALLBACK_STATUS</a> value that indicates how the bounds exception was processed by the callback function.

## Remarks

Drivers can supply a <i>BoundCallback</i> that is called when the system issues a bounds exception.

Use <a href="https://msdn.microsoft.com/library/windows/hardware/dn957856">KeRegisterBoundCallback</a> to register a <i>BoundCallback</i> routine. A driver can subsequently remove the callback by using the <a href="https://msdn.microsoft.com/library/windows/hardware/dn957855">KeDeregisterBoundCallback</a> routine. If the driver can be unloaded, it must remove any registered callbacks in its <a href="https://msdn.microsoft.com/library/windows/hardware/ff564886">Unload</a> routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 10.  |
| **Target Platform** | Windows |
| **Header** | wdm.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn957855">KeDeregisterBoundCallback</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn957856">KeRegisterBoundCallback</a>