---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES
title: "_NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES"
author: windows-driver-content
description: An NDIS miniport driver sets up an NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure to define task offload and connection offload attributes, if any, that are associated with a miniport adapter.
old-location: netvista\ndis_miniport_adapter_offload_attributes.htm
old-project: netvista
ms.assetid: 9ce875fc-ed3f-43e9-bfbc-081f02cb1999
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, miniport_structures_ref_71ee0bdb-903e-4554-915b-010abe803fb3.xml, ndis/NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, netvista.ndis_miniport_adapter_offload_attributes"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure
An NDIS miniport driver sets up an NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure to define task
  offload and connection offload attributes, if any, that are associated with a miniport adapter.

## Syntax
````
typedef struct _NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES {
  NDIS_OBJECT_HEADER           Header;
  PNDIS_OFFLOAD                DefaultOffloadConfiguration;
  PNDIS_OFFLOAD                HardwareOffloadCapabilities;
  PNDIS_TCP_CONNECTION_OFFLOAD DefaultTcpConnectionOffloadConfiguration;
  PNDIS_TCP_CONNECTION_OFFLOAD TcpConnectionOffloadHardwareCapabilities;
} NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES;
````

## Members


`DefaultOffloadConfiguration`

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a> structure that indicates the
     current offload capabilities that are provided by the miniport adapter.

`DefaultTcpConnectionOffloadConfiguration`

A pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_tcp_connection_offload.md">
     NDIS_TCP_CONNECTION_OFFLOAD</a> structure that indicates the current connection offload capabilities
     that are provided by the miniport adapter.

`HardwareOffloadCapabilities`

A pointer to an NDIS_OFFLOAD structure that indicates all the task offload capabilites that are
     supported by the miniport adapter. These capabilities include capabilities that are currently disabled
     by standardized keywords in the registry.

`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES, the 
     <b>Revision</b> member to NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES_REVISION_1.

`TcpConnectionOffloadHardwareCapabilities`

A pointer to an NDIS_TCP_CONNECTION_OFFLOAD structure that indicates all the connection offload
     capabilites that are supported by the miniport adapter. These capabilities include capabilities that are
     currently disabled by standardized keywords in the registry.

## Remarks
A miniport driver that supports task offload or connection offload passes a pointer to an
    NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure in the 
    <i>MiniportAttributes</i> parameter of the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function. A miniport driver calls 
    <b>NdisMSetMiniportAttributes</b> from its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function
    during initialization.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559004">NDIS_TASK_OFFLOAD_HEADER</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_tcp_connection_offload.md">NDIS_TCP_CONNECTION_OFFLOAD</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_offload.md">NDIS_OFFLOAD</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_OFFLOAD_ATTRIBUTES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>