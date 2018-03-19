---
UID: NS:ucxusbdevice._USBDEVICE_ENABLE_FAILURE_FLAGS
title: "_USBDEVICE_ENABLE_FAILURE_FLAGS"
author: windows-driver-content
description: The flags that are set by the client driver in the EVT_UCX_USBDEVICE_ENABLE callback function. Indicate errors, if any, that might have occurred while enabling the device.
old-location: buses\_usbdevice_enable_failure_flags.htm
old-project: usbref
ms.assetid: B239E637-2920-48A5-9F45-D3089140C8A2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: P_USBDEVICE_ENABLE_FAILURE_FLAGS, P_USBDEVICE_ENABLE_FAILURE_FLAGS structure pointer [Buses], USBDEVICE_ENABLE_FAILURE_FLAGS, USBDEVICE_ENABLE_FAILURE_FLAGS structure [Buses], _USBDEVICE_ENABLE_FAILURE_FLAGS, buses._usbdevice_enable_failure_flags, ucxusbdevice/P_USBDEVICE_ENABLE_FAILURE_FLAGS, ucxusbdevice/_USBDEVICE_ENABLE_FAILURE_FLAGS
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
-	USBDEVICE_ENABLE_FAILURE_FLAGS
product: Windows
targetos: Windows
req.typenames: USBDEVICE_ENABLE_FAILURE_FLAGS
req.product: Windows 10 or later.
---

# _USBDEVICE_ENABLE_FAILURE_FLAGS structure
The flags that are set by the client driver in the  <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a> callback function. Indicate errors, if any, that might have occurred while enabling the device.

## Syntax
````
typedef struct _USBDEVICE_ENABLE_FAILURE_FLAGS {
  ULONG InsufficientHardwareResourcesForDefaultEndpoint  :1;
  ULONG InsufficientHardwareResourcesForDevice  :1;
  ULONG Reserved  :30;
} USBDEVICE_ENABLE_FAILURE_FLAGS, *P_USBDEVICE_ENABLE_FAILURE_FLAGS;
````

## Members


`InsufficientHardwareResourcesForDefaultEndpoint`

Insufficient  hardware resources for  transfers to the default endpoint.

`InsufficientHardwareResourcesForDevice`

Insufficient hardware resources to enable transfers.

`Reserved`

Do not use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxusbdevice.h (include Ucxclass.h) |

## See Also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_enable.md">USBDEVICE_ENABLE</a>



<a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_enable.md">EVT_UCX_USBDEVICE_ENABLE</a>