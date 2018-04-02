---
UID: NS:wwan._WWAN_DEVICE_SERVICE_EVENT
title: "_WWAN_DEVICE_SERVICE_EVENT"
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.
old-location: netvista\wwan_device_service_event.htm
old-project: netvista
ms.assetid: 7E02DDE0-7D55-4FBD-879E-EFBA6A517D86
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_EVENT, PWWAN_DEVICE_SERVICE_EVENT, PWWAN_DEVICE_SERVICE_EVENT structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_EVENT, WWAN_DEVICE_SERVICE_EVENT structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_EVENT, netvista.wwan_device_service_event, wwan/PWWAN_DEVICE_SERVICE_EVENT, wwan/WWAN_DEVICE_SERVICE_EVENT"
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
-	WWAN_DEVICE_SERVICE_EVENT
product: Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_EVENT, *PWWAN_DEVICE_SERVICE_EVENT
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_EVENT structure
The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.

## Syntax
```
typedef struct _WWAN_DEVICE_SERVICE_EVENT {
  GUID  DeviceServiceGuid;
  ULONG EventID;
  ULONG uDataSize;
} WWAN_DEVICE_SERVICE_EVENT, *PWWAN_DEVICE_SERVICE_EVENT;
```

## Members


`DeviceServiceGuid`

The GUID of the device service that the event originated from.

`EventID`

The ID for the event.

`uDataSize`

The size, in bytes, of the device service event data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxCommandDataSize</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh831880">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh831880">WWAN_SUPPORTED_DEVICE_SERVICES</a>