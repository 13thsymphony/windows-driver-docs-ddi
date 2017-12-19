---
UID: NS.WWAN._WWAN_DEVICE_SERVICE_EVENT
title: _WWAN_DEVICE_SERVICE_EVENT
author: windows-driver-content
description: The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.
old-location: netvista\wwan_device_service_event.htm
old-project: NetVista
ms.assetid: 7E02DDE0-7D55-4FBD-879E-EFBA6A517D86
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _WWAN_DEVICE_SERVICE_EVENT, PWWAN_DEVICE_SERVICE_EVENT, *PWWAN_DEVICE_SERVICE_EVENT, WWAN_DEVICE_SERVICE_EVENT
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
req.alt-api: WWAN_DEVICE_SERVICE_EVENT
req.alt-loc: wwan.h
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
req.product: Windows 10 or later.
---

# _WWAN_DEVICE_SERVICE_EVENT structure



## -description
The WWAN_DEVICE_SERVICE_EVENT structure represents an unsolicited device service event.



## -syntax

````
typedef struct _WWAN_DEVICE_SERVICE_EVENT {
  GUID  DeviceServiceGuid;
  ULONG EventID;
  ULONG uDataSize;
} WWAN_DEVICE_SERVICE_EVENT, *PWWAN_DEVICE_SERVICE_EVENT;
````


## -struct-fields

### -field DeviceServiceGuid

The GUID of the device service that the event originated from.


### -field EventID

The ID for the event.


### -field uDataSize

The size, in bytes, of the device service event data that follows the structure instance in memory. This value should not exceed the value of the <b>uMaxCommandDataSize</b> member of the <a href="netvista.wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a> structure.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported starting with  Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wwan.h (include Wwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_supported_device_services">WWAN_SUPPORTED_DEVICE_SERVICES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20WWAN_DEVICE_SERVICE_EVENT structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

