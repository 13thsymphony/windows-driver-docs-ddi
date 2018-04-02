---
UID: NF:usbdlib.COMPOSITE_DEVICE_CAPABILITIES_INIT
title: COMPOSITE_DEVICE_CAPABILITIES_INIT function
author: windows-driver-content
description: The COMPOSITE_DEVICE_CAPABILITIES_INIT macro initializes the COMPOSITE_DEVICE_CAPABILITIES structure.
old-location: buses\composite_driver_capabilities_init.htm
old-project: usbref
ms.assetid: 92DDF65E-4B5B-443A-9C90-3B1BB2DD3CAF
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: COMPOSITE_DEVICE_CAPABILITIES_INIT, COMPOSITE_DEVICE_CAPABILITIES_INIT routine [Buses], buses.composite_driver_capabilities_init, usbdlib/COMPOSITE_DEVICE_CAPABILITIES_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Usbdex.lib
-	Usbdex.dll
api_name:
-	COMPOSITE_DEVICE_CAPABILITIES_INIT
product:
- Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---


# COMPOSITE_DEVICE_CAPABILITIES_INIT function
The <b>COMPOSITE_DEVICE_CAPABILITIES_INIT</b> macro initializes the <a href="https://msdn.microsoft.com/3C1BF8C6-3489-4636-9B3F-B0C2C1327466">COMPOSITE_DEVICE_CAPABILITIES</a> structure.

## Syntax

```
void COMPOSITE_DEVICE_CAPABILITIES_INIT(
  PCOMPOSITE_DEVICE_CAPABILITIES CapabilityFlags
);
```

## Parameters

`CapabilityFlags`

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/3C1BF8C6-3489-4636-9B3F-B0C2C1327466">COMPOSITE_DEVICE_CAPABILITIES</a> structure to be initialized. The macro sets the <b>CompositeDriverCapabilityFunctionSuspend</b>
member of <b>COMPOSITE_DEVICE_CAPABILITIES</b> to 0.


## Return Value

This routine does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.  |
| **Target Platform** | Desktop |
| **Header** | usbdlib.h |
| **Library** | Usbdex.lib |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/3C1BF8C6-3489-4636-9B3F-B0C2C1327466">COMPOSITE_DEVICE_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a>