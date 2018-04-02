---
UID: NS:udecxusbendpoint._UDECX_USB_ENDPOINT_CALLBACKS
title: "_UDECX_USB_ENDPOINT_CALLBACKS"
author: windows-driver-content
description: Contains function pointers to endpoint callback functions implemented by the UDE client driver. Initialize this structure by calling UDECX_USB_ENDPOINT_CALLBACKS_INIT.
old-location: buses\udecx_usb_endpoint_callbacks.htm
old-project: usbref
ms.assetid: 5AAB4474-9FDF-4ACF-AC38-F84D2682B5E0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUDECX_USB_ENDPOINT_CALLBACKS, PUDECX_USB_ENDPOINT_CALLBACKS, PUDECX_USB_ENDPOINT_CALLBACKS structure pointer [Buses], UDECX_USB_ENDPOINT_CALLBACKS, UDECX_USB_ENDPOINT_CALLBACKS structure [Buses], _UDECX_USB_ENDPOINT_CALLBACKS, buses.udecx_usb_endpoint_callbacks, udecxusbendpoint/PUDECX_USB_ENDPOINT_CALLBACKS, udecxusbendpoint/UDECX_USB_ENDPOINT_CALLBACKS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: udecxusbendpoint.h
req.include-header: Udecx.h
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	udecxusbendpoint.h
api_name:
-	UDECX_USB_ENDPOINT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: UDECX_USB_ENDPOINT_CALLBACKS, *PUDECX_USB_ENDPOINT_CALLBACKS
req.product: Windows 10 or later.
---

# _UDECX_USB_ENDPOINT_CALLBACKS structure
Contains function pointers to endpoint callback functions implemented by the UDE client driver. Initialize this structure by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt628006">UDECX_USB_ENDPOINT_CALLBACKS_INIT</a>.

## Syntax
```
typedef struct _UDECX_USB_ENDPOINT_CALLBACKS {
  ULONG                        Size;
  PFN_UDECX_USB_ENDPOINT_RESET EvtUsbEndpointReset;
  PFN_UDECX_USB_ENDPOINT_START EvtUsbEndpointStart;
  PFN_UDECX_USB_ENDPOINT_PURGE EvtUsbEndpointPurge;
} UDECX_USB_ENDPOINT_CALLBACKS, *PUDECX_USB_ENDPOINT_CALLBACKS;
```

## Members


`Size`

The size of this structure.

`EvtUsbEndpointReset`

Required. A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595917">EVT_UDECX_USB_ENDPOINT_RESET</a> callback function implemented by a UDE client driver.

`EvtUsbEndpointStart`

Optional. A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595918">EVT_UDECX_USB_ENDPOINT_START</a> callback function implemented by a UDE client driver.

`EvtUsbEndpointPurge`

Optional. A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/mt595916">EVT_UDECX_USB_ENDPOINT_PURGE</a> callback function implemented by a UDE client driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | udecxusbendpoint.h (include Udecx.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt627983">UdecxUsbEndpointCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt627985">UdecxUsbEndpointInitSetCallbacks</a>