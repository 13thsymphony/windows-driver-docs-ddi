---
UID: NS:wwan._WWAN_DEVICE_SERVICE_RESPONSE
title: "_WWAN_DEVICE_SERVICE_RESPONSE"
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_RESPONSE structure represents a response from a device service.
old-location: netvista\wwan_device_service_response.htm
old-project: netvista
ms.assetid: FCDAEE07-B10E-491B-9BDB-49D77444281D
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_RESPONSE, PWWAN_DEVICE_SERVICE_RESPONSE, PWWAN_DEVICE_SERVICE_RESPONSE structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_RESPONSE, WWAN_DEVICE_SERVICE_RESPONSE structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_RESPONSE, netvista.wwan_device_service_response, wwan/PWWAN_DEVICE_SERVICE_RESPONSE, wwan/WWAN_DEVICE_SERVICE_RESPONSE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wwan.h
req.include-header: Wwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
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
-	wwan.h
api_name:
-	WWAN_DEVICE_SERVICE_RESPONSE
product:
- Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_RESPONSE, *PWWAN_DEVICE_SERVICE_RESPONSE
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_RESPONSE structure
The WWAN_DEVICE_SERVICE_RESPONSE structure represents a response from a device service.

## Syntax
```
typedef struct _WWAN_DEVICE_SERVICE_RESPONSE {
  GUID  DeviceServiceGuid;
  ULONG ResponseID;
  ULONG uDataSize;
} *PWWAN_DEVICE_SERVICE_RESPONSE, WWAN_DEVICE_SERVICE_RESPONSE;
```

## Members


`DeviceServiceGuid`

The GUID of the device service that the response originated from.

`ResponseID`

The ID of the response.

`uDataSize`

The size, in bytes, of the device service response data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxCommandDataSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh831880">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh831880">WWAN_SUPPORTED_DEVICE_SERVICES</a>