---
UID: NS.NDISWWAN._NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
title: _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
author: windows-driver-content
description: The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure represents the status of a device service session write operation.
old-location: netvista\ndis_wwan_device_service_session_write_complete.htm
old-project: NetVista
ms.assetid: 16A48882-BEA6-4F95-8E9F-572BFD102031
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
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
req.alt-api: NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
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

# _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure



## -description
The NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE structure represents the status of a device service session write operation.



## -syntax

````
typedef struct _NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE {
  NDIS_OBJECT_HEADER Header;
  WWAN_STATUS        uStatus;
} NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE, *PNDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE;
````


## -struct-fields

### -field Header

The header with type, revision, and size information about the NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE
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
NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE_REVISION_1

</td>
</tr>
<tr>
<td>
Size

</td>
<td>
sizeof(NDIS_WWAN_DEVICE_SERVICE_SESSION_WRITE_COMPLETE)

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field uStatus

The status of the completion of the write operation.


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