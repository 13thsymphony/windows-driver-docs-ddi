---
UID : NS:ndis._NDIS_BIND_FAILED_NOTIFICATION
title : _NDIS_BIND_FAILED_NOTIFICATION
author : windows-driver-content
description : The NDIS_BIND_FAILED_NOTIFICATION structure describes a binding event failure.
old-location : netvista\ndis_bind_failed_notification.htm
old-project : netvista
ms.assetid : 5420839B-EB81-43CC-B7BD-9D1FA2560A3D
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : NDIS_BIND_FAILED_NOTIFICATION, ndis/PNDIS_BIND_FAILED_NOTIFICATION, *PNDIS_BIND_FAILED_NOTIFICATION, ndis/NDIS_BIND_FAILED_NOTIFICATION, _NDIS_BIND_FAILED_NOTIFICATION, NDIS_BIND_FAILED_NOTIFICATION structure [Network Drivers Starting with Windows Vista], netvista.ndis_bind_failed_notification, PNDIS_BIND_FAILED_NOTIFICATION, PNDIS_BIND_FAILED_NOTIFICATION structure pointer [Network Drivers Starting with Windows Vista]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : ndis.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Supported in NDIS 6.30 and later.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : See Remarks section
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : NDIS_BIND_FAILED_NOTIFICATION, *PNDIS_BIND_FAILED_NOTIFICATION
---

# _NDIS_BIND_FAILED_NOTIFICATION structure
The <b>NDIS_BIND_FAILED_NOTIFICATION</b> structure describes a binding event failure.

## Syntax
````
typedef struct _NDIS_BIND_FAILED_NOTIFICATION {
  NDIS_OBJECT_HEADER Header;
  NET_LUID           MiniportNetLuid;
} NDIS_BIND_FAILED_NOTIFICATION, *PNDIS_BIND_FAILED_NOTIFICATION;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_BIND_FAILED_NOTIFICATION</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_DEFAULT</b>, the 
     <b>Revision</b> member to <b>NDIS_BIND_FAILED_NOTIFICATION_REVISION_1</b>, and the 
     <b>Size</b> member to <b>NDIS_SIZEOF_NDIS_BIND_FAILED_NOTIFICATION_REVISION_1</b>.

`MiniportNetLuid`

The NDIS network interface
     name (<i>ifName</i> in RFC 2863) of the miniport adapter.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | ndis.h (include Ndis.h) |