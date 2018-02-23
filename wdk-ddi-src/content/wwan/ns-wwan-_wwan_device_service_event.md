---
UID: NS:wwan._WWAN_DEVICE_SERVICE_EVENT
title: "_WWAN_DEVICE_SERVICE_EVENT"
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.
old-location: netvista\wwan_device_service_event.htm
old-project: netvista
ms.assetid: 7E02DDE0-7D55-4FBD-879E-EFBA6A517D86
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: WWAN_DEVICE_SERVICE_EVENT structure [Network Drivers Starting with Windows Vista], WWAN_DEVICE_SERVICE_EVENT, *PWWAN_DEVICE_SERVICE_EVENT, _WWAN_DEVICE_SERVICE_EVENT, wwan/PWWAN_DEVICE_SERVICE_EVENT, PWWAN_DEVICE_SERVICE_EVENT, PWWAN_DEVICE_SERVICE_EVENT structure pointer [Network Drivers Starting with Windows Vista], wwan/WWAN_DEVICE_SERVICE_EVENT, netvista.wwan_device_service_event
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wwan.h
apiname:
-	WWAN_DEVICE_SERVICE_EVENT
product: Windows
targetos: Windows
req.typenames: "*PWWAN_DEVICE_SERVICE_EVENT, WWAN_DEVICE_SERVICE_EVENT"
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_EVENT structure
The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.

## Syntax
````
typedef struct _WWAN_DEVICE_SERVICE_EVENT {
  GUID  DeviceServiceGuid;
  ULONG EventID;
  ULONG uDataSize;
} WWAN_DEVICE_SERVICE_EVENT, *PWWAN_DEVICE_SERVICE_EVENT;
````

## Members


`DeviceServiceGuid`

The GUID of the device service that the event originated from.

`EventID`

The ID for the event.

`uDataSize`

The size, in bytes, of the device service event data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxCommandDataSize</b> member of the <a href="..\wwan\ns-wwan-_wwan_supported_device_services.md">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with  Windows 8. Supported starting with  Windows 8. |
| **Header** | wwan.h (include Wwan.h) |

## See Also

<a href="..\wwan\ns-wwan-_wwan_supported_device_services.md">WWAN_SUPPORTED_DEVICE_SERVICES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WWAN_DEVICE_SERVICE_EVENT structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>