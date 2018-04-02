---
UID: NS:ucxusbdevice._USBDEVICE_RESET
title: "_USBDEVICE_RESET"
author: windows-driver-content
description: Contains parameters for a request to reset the specified device. This structure is passed by UCX in request parameters (Parameters.Others.Arg1) of a framework request object of the EVT_UCX_USBDEVICE_RESET callback function.
old-location: buses\_usbdevice_reset.htm
old-project: usbref
ms.assetid: 4C07239D-89AE-4A9F-B7EB-CFFE6D47F10B
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PUSBDEVICE_RESET, P_USBDEVICE_RESET, P_USBDEVICE_RESET structure pointer [Buses], USBDEVICE_RESET, USBDEVICE_RESET structure [Buses], _USBDEVICE_RESET, buses._usbdevice_reset, ucxusbdevice/P_USBDEVICE_RESET, ucxusbdevice/_USBDEVICE_RESET"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxusbdevice.h
api_name:
-	USBDEVICE_RESET
product:
- Windows
targetos: Windows
req.typenames: USBDEVICE_RESET, *PUSBDEVICE_RESET
req.product: Windows 10 or later.
---

# _USBDEVICE_RESET structure
Contains parameters for a request to reset the specified device.  This structure is passed by UCX in request parameters (<b>Parameters.Others.Arg1</b>) of a framework request object of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187845">EVT_UCX_USBDEVICE_RESET</a> callback function.

## Syntax
```
typedef struct _USBDEVICE_RESET {
  USBDEVICE_MGMT_HEADER Header;
  UCXENDPOINT           DefaultEndpoint;
  ULONG                 EndpointsToDisableCount;
  UCXENDPOINT           *EndpointsToDisable;
} *PUSBDEVICE_RESET, USBDEVICE_RESET;
```

## Members


`Header`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that contains  the handle for the USB hub or device.

`DefaultEndpoint`

The default endpoint for the USB hub or device.

`EndpointsToDisableCount`

The number of endpoints to disable.

`EndpointsToDisable`

A pointer to an array of handles to endpoints to disable.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187845">EVT_UCX_USBDEVICE_RESET</a>