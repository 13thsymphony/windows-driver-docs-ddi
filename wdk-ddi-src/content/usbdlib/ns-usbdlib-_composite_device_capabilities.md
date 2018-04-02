---
UID: NS:usbdlib._COMPOSITE_DEVICE_CAPABILITIES
title: "_COMPOSITE_DEVICE_CAPABILITIES"
author: windows-driver-content
description: The COMPOSITE_DEVICE_CAPABILITIES structure specifies the capabilities of the driver of a USB multi-function device (composite driver). To initialize the structure, use the COMPOSITE_DEVICE_CAPABILITIES_INIT macro.
old-location: buses\composite_driver_capabilities.htm
old-project: usbref
ms.assetid: 3C1BF8C6-3489-4636-9B3F-B0C2C1327466
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PCOMPOSITE_DEVICE_CAPABILITIES, COMPOSITE_DEVICE_CAPABILITIES, COMPOSITE_DEVICE_CAPABILITIES structure [Buses], PCOMPOSITE_DEVICE_CAPABILITIES, PCOMPOSITE_DEVICE_CAPABILITIES structure pointer [Buses], _COMPOSITE_DEVICE_CAPABILITIES, buses.composite_driver_capabilities, usbdlib/COMPOSITE_DEVICE_CAPABILITIES, usbdlib/PCOMPOSITE_DEVICE_CAPABILITIES"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: usbdlib.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 8.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbdlib.h
api_name:
-	COMPOSITE_DEVICE_CAPABILITIES
product: Windows
targetos: Windows
req.typenames: COMPOSITE_DEVICE_CAPABILITIES, *PCOMPOSITE_DEVICE_CAPABILITIES
req.product: Windows 10 or later.
---

# _COMPOSITE_DEVICE_CAPABILITIES structure
The <b>COMPOSITE_DEVICE_CAPABILITIES</b> structure specifies the capabilities of the  driver of a USB multi-function device (composite driver). To initialize the structure, use the <a href="https://msdn.microsoft.com/library/windows/hardware/hh450803">COMPOSITE_DEVICE_CAPABILITIES_INIT</a> macro.

## Syntax
```
typedef struct _COMPOSITE_DEVICE_CAPABILITIES {
  ULONG  : 1  CapabilityFunctionSuspend;
  ULONG  : 31 Reserved;
} *PCOMPOSITE_DEVICE_CAPABILITIES, COMPOSITE_DEVICE_CAPABILITIES;
```

## Members


`CapabilityFunctionSuspend`

If set to 1, indicates that the composite driver supports the USB function suspend feature.

`Reserved`

Reserved.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8. Windows 8. |
| **Header** | usbdlib.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450803">COMPOSITE_DEVICE_CAPABILITIES_INIT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450897">How to Register a Composite Device</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450854">IOCTL_INTERNAL_USB_REGISTER_COMPOSITE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh450898">REGISTER_COMPOSITE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406229">USBD_BuildRegisterCompositeDevice</a>