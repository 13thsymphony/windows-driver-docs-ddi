---
UID: NS:wwan._WWAN_DEVICE_SERVICE_SESSION
title: "_WWAN_DEVICE_SERVICE_SESSION"
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_SESSION structure represents the state of a device service session, or the operation to be performed on a device service.
old-location: netvista\wwan_device_service_session.htm
old-project: netvista
ms.assetid: 29EEB068-EFFB-42BF-8D92-D56D010DE46A
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWWAN_DEVICE_SERVICE_SESSION, PWWAN_DEVICE_SERVICE_SESSION, PWWAN_DEVICE_SERVICE_SESSION structure pointer [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_SESSION, WWAN_DEVICE_SERVICE_SESSION structure [Network Drivers Starting with Windows Vista], _WWAN_DEVICE_SERVICE_SESSION, netvista.wwan_device_service_session, wwan/PWWAN_DEVICE_SERVICE_SESSION, wwan/WWAN_DEVICE_SERVICE_SESSION"
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
-	WWAN_DEVICE_SERVICE_SESSION
product: Windows
targetos: Windows
req.typenames: WWAN_DEVICE_SERVICE_SESSION, *PWWAN_DEVICE_SERVICE_SESSION
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_SESSION structure
The WWAN_DEVICE_SERVICE_SESSION structure represents the state of a device service session, or the operation to be performed on a device service.

## Syntax
```
typedef struct _WWAN_DEVICE_SERVICE_SESSION {
  GUID                              DeviceServiceGuid;
  WWAN_DEVICE_SERVICE_SESSION_STATE State;
  ULONG                             uSessionID;
} WWAN_DEVICE_SERVICE_SESSION, *PWWAN_DEVICE_SERVICE_SESSION;
```

## Members


`DeviceServiceGuid`

The GUID of the device service on which to perform the operation.

`State`

The state of, or action, for the device service session.

`uSessionID`

The session ID for the device service session.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh831858">NDIS_WWAN_DEVICE_SERVICE_SESSION_INFO</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831865">NDIS_WWAN_SET_DEVICE_SERVICE_SESSION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh831876">WWAN_DEVICE_SERVICE_SESSION_STATE</a>