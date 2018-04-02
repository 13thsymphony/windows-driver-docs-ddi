---
UID: NS:ucxendpoint._ENDPOINTS_CONFIGURE
title: "_ENDPOINTS_CONFIGURE"
author: windows-driver-content
description: Describes endpoints to enable or disable endpoints. This structure is passed by UCX in the EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function.
old-location: buses\_endpoints_configure.htm
old-project: usbref
ms.assetid: C24B7D85-AEA9-43B3-9BEE-262CAA255834
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PENDPOINTS_CONFIGURE, ENDPOINTS_CONFIGURE, ENDPOINTS_CONFIGURE structure [Buses], P_ENDPOINTS_CONFIGURE, P_ENDPOINTS_CONFIGURE structure pointer [Buses], _ENDPOINTS_CONFIGURE, buses._endpoints_configure, ucxendpoint/P_ENDPOINTS_CONFIGURE, ucxendpoint/_ENDPOINTS_CONFIGURE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
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
-	ucxendpoint.h
api_name:
-	ENDPOINTS_CONFIGURE
product: Windows
targetos: Windows
req.typenames: ENDPOINTS_CONFIGURE, *PENDPOINTS_CONFIGURE
req.product: Windows 10 or later.
---

# _ENDPOINTS_CONFIGURE structure
Describes   endpoints to enable or disable endpoints. This structure is passed by UCX in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt187842">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a>  callback function.

## Syntax
```
typedef struct _ENDPOINTS_CONFIGURE {
  USBDEVICE_MGMT_HEADER             Header;
  ULONG                             EndpointsToEnableCount;
  UCXENDPOINT                       *EndpointsToEnable;
  ULONG                             EndpointsToDisableCount;
  UCXENDPOINT                       *EndpointsToDisable;
  ULONG                             EndpointsEnabledAndUnchangedCount;
  UCXENDPOINT                       *EndpointsEnabledAndUnchanged;
  ENDPOINTS_CONFIGURE_FAILURE_FLAGS FailureFlags;
  ULONG                             ExitLatencyDelta;
  UCHAR                             ConfigurationValue;
  UCHAR                             InterfaceNumber;
  UCHAR                             AlternateSetting;
  ULONG                             Reserved1;
  PVOID                             Reserved2;
} ENDPOINTS_CONFIGURE, *PENDPOINTS_CONFIGURE;
```

## Members


`Header`

A <a href="https://msdn.microsoft.com/library/windows/hardware/mt188075">USBDEVICE_MGMT_HEADER</a> structure that stores handles to the USB hub or device whose endpoints.

`EndpointsToEnableCount`

The number of endpoints to configure.

`EndpointsToEnable`

A pointer to the first endpoint handle in the array of endpoints to  enable.

`EndpointsToDisableCount`

The number of endpoints to configure.

`EndpointsToDisable`

A pointer to the first endpoint handle in the array of endpoints to  enable.

`EndpointsEnabledAndUnchangedCount`

The number of endpoints that were enabled and unchanged.

`EndpointsEnabledAndUnchanged`

A pointer to the first endpoint handle in the array of endpoints that have not been changed.

`FailureFlags`

The errors, if any, that might occur when attempting to configure endpoints for the USB device or hub.

`ExitLatencyDelta`

The Exit Latency Delta (ELD) value. For more information see section 4.6.6.1 of the eXtensible Host Controller Interface specification.

`ConfigurationValue`

The configuration number of the USB configuration that contains the endpoints.

`InterfaceNumber`

The interface number of the USB interface that contains the endpoints.

`AlternateSetting`

The setting number of the alternate setting that contains the endpoints.

`Reserved1`



`Reserved2`




## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt187842">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a>