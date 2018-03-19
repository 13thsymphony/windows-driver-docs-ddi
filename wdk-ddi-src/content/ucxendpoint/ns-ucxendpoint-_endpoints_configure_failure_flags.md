---
UID: NS:ucxendpoint._ENDPOINTS_CONFIGURE_FAILURE_FLAGS
title: "_ENDPOINTS_CONFIGURE_FAILURE_FLAGS"
author: windows-driver-content
description: This structure provides failure flags to indicate errors, if any, that might have occurred during a request to an EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE callback function.
old-location: buses\_endpoints_configure_failure_flags.htm
old-project: usbref
ms.assetid: D605A20B-3747-458E-BA9D-F723F884F130
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ENDPOINTS_CONFIGURE_FAILURE_FLAGS, ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure [Buses], P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS, P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure pointer [Buses], _ENDPOINTS_CONFIGURE_FAILURE_FLAGS, buses._endpoints_configure_failure_flags, ucxendpoint/P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS, ucxendpoint/_ENDPOINTS_CONFIGURE_FAILURE_FLAGS
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
-	ENDPOINTS_CONFIGURE_FAILURE_FLAGS
product: Windows
targetos: Windows
req.typenames: ENDPOINTS_CONFIGURE_FAILURE_FLAGS
req.product: Windows 10 or later.
---

# _ENDPOINTS_CONFIGURE_FAILURE_FLAGS structure
This structure provides failure flags to indicate errors, if any, that might have occurred during a request to an <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_endpoints_configure.md">EVT_UCX_USBDEVICE_ENDPOINTS_CONFIGURE</a> callback function.

## Syntax
````
typedef struct _ENDPOINTS_CONFIGURE_FAILURE_FLAGS {
  ULONG InsufficientBandwidth  :1;
  ULONG InsufficientHardwareResourcesForEndpoints  :1;
  ULONG MaxExitLatencyTooLarge  :1;
  ULONG Reserved  :29;
} ENDPOINTS_CONFIGURE_FAILURE_FLAGS, *P_ENDPOINTS_CONFIGURE_FAILURE_FLAGS;
````

## Members


`InsufficientBandwidth`

Insufficient bandwidth to configure the specified endpoints.

`InsufficientHardwareResourcesForEndpoints`

Insufficient hardware resources to configure the specified endpoints.

`MaxExitLatencyTooLarge`

The maximum exit latency is too large to configure the specified endpoints.

`Reserved`

Do not use.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |

## See Also

<a href="..\ucxendpoint\ns-ucxendpoint-_endpoints_configure.md">ENDPOINTS_CONFIGURE</a>