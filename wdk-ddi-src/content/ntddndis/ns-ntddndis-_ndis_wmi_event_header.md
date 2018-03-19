---
UID: NS:ntddndis._NDIS_WMI_EVENT_HEADER
title: "_NDIS_WMI_EVENT_HEADER"
author: windows-driver-content
description: The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.
old-location: netvista\ndis_wmi_event_header.htm
old-project: netvista
ms.assetid: b9e2c393-cf77-4193-ba59-b8eb914ef1e6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_WMI_EVENT_HEADER, NDIS_WMI_EVENT_HEADER, NDIS_WMI_EVENT_HEADER structure [Network Drivers Starting with Windows Vista], PNDIS_WMI_EVENT_HEADER, PNDIS_WMI_EVENT_HEADER structure pointer [Network Drivers Starting with Windows Vista], _NDIS_WMI_EVENT_HEADER, ndis_wmi_ref_ebe1bff7-7e6d-47e7-b79c-3e53a733ac54.xml, netvista.ndis_wmi_event_header, ntddndis/NDIS_WMI_EVENT_HEADER, ntddndis/PNDIS_WMI_EVENT_HEADER"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddndis.h
api_name:
-	NDIS_WMI_EVENT_HEADER
product: Windows
targetos: Windows
req.typenames: NDIS_WMI_EVENT_HEADER, *PNDIS_WMI_EVENT_HEADER
---

# _NDIS_WMI_EVENT_HEADER structure
The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.

## Syntax
````
typedef struct _NDIS_WMI_EVENT_HEADER {
  NDIS_OBJECT_HEADER Header;
  NET_IFINDEX        IfIndex;
  NET_LUID           NetLuid;
  ULONG64            RequestId;
  NDIS_PORT_NUMBER   PortNumber;
  ULONG              DeviceNameLength;
  ULONG              DeviceNameOffset;
  UCHAR              Padding[4];
} NDIS_WMI_EVENT_HEADER, *PNDIS_WMI_EVENT_HEADER;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for this
     NDIS_WMI_EVENT_HEADER structure. Set the 
     <b>Type</b> member of NDIS_OBJECT_HEADER to NDIS_WMI_OBJECT_TYPE_EVENT, the 
     <b>Revision</b> member to NDIS_WMI_EVENT_HEADER_REVISION_1, and the 
     <b>Size</b> member to 
     sizeof(NDIS_WMI_EVENT_HEADER).

`IfIndex`

The NDIS interface index of the NDIS miniport adapter interface that is associated with the
     GUID.

`NetLuid`

The NDIS network interface name of the miniport adapter.

`RequestId`

An identifier for the request. If a miniport driver must complete a request immediately and it
     completes the request with a status of NDIS_STATUS_INDICATION_REQUIRED, the miniport driver uses this 
     <b>RequestId</b> value to set the 
     <b>RequestId</b> member of the associated 
     <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a> structure. 
     

NDIS or overlying drivers can also use the 
     <b>RequestId</b> to cancel a request. When a miniport driver receives a
     cancellation request, the miniport driver cancels any pending requests with a matching 
     <b>RequestId</b>. If 
     <b>RequestId</b> is zero, the miniport driver can ignore this member.

For more information about this member, see 
     <a href="..\ndis\ns-ndis-_ndis_oid_request.md">NDIS_OID_REQUEST</a>.

`PortNumber`

The miniport adapter port, if any. If the GUID is not specific to a port, 
     <b>PortNumber</b> is zero.

`DeviceNameLength`

The length, in bytes, of the device name.

`DeviceNameOffset`

The offset, in bytes, to the beginning of the device name from the beginning of the
     NDIS_WMI_EVENT_HEADER structure.

`Padding`

This member is reserved.

## Remarks
NDIS translates NDIS status indications to WMI GUID event indications.

WMI GUID event indications that are specific to NDIS 6.0 and later versions include an
    NDIS_WMI_EVENT_HEADER structure that is followed by the GUID-specific data, if any.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ntddndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>