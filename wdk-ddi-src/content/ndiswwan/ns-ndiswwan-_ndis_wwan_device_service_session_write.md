---
UID: NS.NDISWWAN._NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
title: _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents device service session data to be sent from the host to the MB device.
old-location: netvista\ndis_wwan_device_service_session_write.htm
old-project: netvista
ms.assetid: BF4A7BF6-6C39-4F75-BF76-848FF9241E52
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndiswwan.h
req.include-header: Ndiswwan.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
req.alt-loc: ndiswwan.h
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
---

# _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure



## -description
The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure represents device service session data to be sent from the host to the MB device.


## -syntax

````
typedef struct _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE {
  NDIS_OBJECT_HEADER                Header;
  WWAN_DEVICE_SERVICE_SESSION_WRITE WriteData;
} NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE
     structure. The MB Service sets the header with the values that are shown in the following table when it
     sends the data structure to the miniport driver for 
     <i>set</i> operations. Miniport drivers must set the header with the same values when they send the data
     structure to the MB service.
     
<table>
<tr>
<th>Header submember</th>
<th>Value</th>
</tr>
<tr>
<td>
Type
</td>
<td>
NDIS_OBJECT_TYPE_DEFAULT
</td>
</tr>
<tr>
<td>
Revision
</td>
<td>
NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_REVISION_1
</td>
</tr>
<tr>
<td>
Size
</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE)
</td>
</tr>
</table>
 
For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.

### -field WriteData

The data to be sent to the MB device.

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
<dt>Ndiswwan.h (include Ndiswwan.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.wwan_device_service_session_write">WWAN_DEVICE_SERVICE_SESSION_WRITE</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
