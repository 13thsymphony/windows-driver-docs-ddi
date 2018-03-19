---
UID: NS:ndis._NDIS_RESTART_GENERAL_ATTRIBUTES
title: "_NDIS_RESTART_GENERAL_ATTRIBUTES"
author: windows-driver-content
description: The NDIS_RESTART_GENERAL_ATTRIBUTES structure defines the general restart attributes that are associated with a miniport adapter.
old-location: netvista\ndis_restart_general_attributes.htm
old-project: netvista
ms.assetid: f67bd2fe-4553-4b1a-8d39-26777bcc60e0
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_RESTART_GENERAL_ATTRIBUTES, NDIS_RESTART_GENERAL_ATTRIBUTES, NDIS_RESTART_GENERAL_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], PNDIS_RESTART_GENERAL_ATTRIBUTES, PNDIS_RESTART_GENERAL_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_RESTART_GENERAL_ATTRIBUTES, miniport_structures_ref_10a54e42-4d48-4fdc-8a68-43771c319215.xml, ndis/NDIS_RESTART_GENERAL_ATTRIBUTES, ndis/PNDIS_RESTART_GENERAL_ATTRIBUTES, netvista.ndis_restart_general_attributes"
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
-	NDIS_RESTART_GENERAL_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: NDIS_RESTART_GENERAL_ATTRIBUTES, *PNDIS_RESTART_GENERAL_ATTRIBUTES
---

# _NDIS_RESTART_GENERAL_ATTRIBUTES structure
The <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure defines the general restart attributes that are
  associated with a miniport adapter.

## Syntax
````
typedef struct _NDIS_RESTART_GENERAL_ATTRIBUTES {
  NDIS_OBJECT_HEADER               Header;
  ULONG                            MtuSize;
  ULONG64                          MaxXmitLinkSpeed;
  ULONG64                          MaxRcvLinkSpeed;
  ULONG                            LookaheadSize;
  ULONG                            MacOptions;
  ULONG                            SupportedPacketFilters;
  ULONG                            MaxMulticastListSize;
  PNDIS_RECEIVE_SCALE_CAPABILITIES RecvScaleCapabilities;
  NET_IF_ACCESS_TYPE               AccessType;
  ULONG                            Flags;
  NET_IF_CONNECTION_TYPE           ConnectionType;
  ULONG                            SupportedStatistics;
  ULONG                            DataBackFillSize;
  ULONG                            ContextBackFillSize;
  PNDIS_OID                        SupportedOidList;
  ULONG                            SupportedOidListLength;
#if (NDIS_SUPPORT_NDIS620)
  ULONG                            MaxLookaheadSizeAccessed;
#endif 
} NDIS_RESTART_GENERAL_ATTRIBUTES, *PNDIS_RESTART_GENERAL_ATTRIBUTES;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to <b>NDIS_OBJECT_TYPE_RESTART_GENERIC_ATTRIBUTES</b>. 
     

To indicate the version of the <b>NDIS_RESTART_GENERAL_ATTRIBUTES</b> structure, NDIS sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_RESTART_GENERAL_ATTRIBUTES_REVISION_2

Added the 
       <b>MaxLookaheadSizeAccessed</b> member for NDIS 6.2. 
       

NDIS sets the 
       <b>Size</b> member to <b>NDIS_SIZEOF_RESTART_GENERAL_ATTRIBUTES_REVISION_2</b>.





#### NDIS_RESTART_GENERAL_ATTRIBUTES_REVISION_1

Original version for NDIS 6.0 and NDIS 6.1.
       

NDIS sets the 
       <b>Size</b> member to <b>NDIS_SIZEOF_RESTART_GENERAL_ATTRIBUTES_REVISION_1</b>.

`MtuSize`

The maximum transfer unit (MTU) size. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569598">OID_GEN_MAXIMUM_FRAME_SIZE</a>.

`MaxXmitLinkSpeed`

The maximum transmit link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.

`MaxRcvLinkSpeed`

The maximum receive link speed of the adapter in bits per second. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>.

`LookaheadSize`

The lookahead size for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569574">OID_GEN_CURRENT_LOOKAHEAD</a>.

`MacOptions`

The medium access control (MAC) options for the miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>.

`SupportedPacketFilters`

The packet filter flags for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
     OID_GEN_SUPPORTED_PACKET_FILTERS</a>.

`MaxMulticastListSize`

The maximum multicast address list size for the miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-802-3-maximum-list-size">
     OID_802_3_MAXIMUM_LIST_SIZE</a>.

`RecvScaleCapabilities`

The receive side scaling (RSS) capabilities of the NIC. If the miniport adapter does not support
     the RSS feature, NDIS sets 
     <b>RecvScaleCapabilities</b> to a pointer to an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_receive_scale_capabilities.md">
     NDIS_RECEIVE_SCALE_CAPABILITIES</a> structure that is filled with zeros. For more information about
     RSS, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-receive-scale-capabilities">
     OID_GEN_RECEIVE_SCALE_CAPABILITIES</a>.

`AccessType`

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a> NDIS network interface
     access type.

`Flags`

Reserved.

`ConnectionType`

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a> NDIS network
     interface connection type.

`SupportedStatistics`

The supported statistics. For more information, see the 
     <b>SupportedStatistics</b> member of the 
     <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
     NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a> structure.

`DataBackFillSize`

The required data backfill size, in bytes, of the driver.

`ContextBackFillSize`

The required context backfill size, in bytes, of the driver.

`SupportedOidList`

A list of OIDs that the miniport driver supports. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a>.

`SupportedOidListLength`

The size, in bytes, of the OID list that is specified in the 
     <b>SupportedOidList</b> member.

`MaxLookaheadSizeAccessed`

A ULONG value for the maximum size, in bytes, of the lookahead size requirement for receive
     queues. A miniport adapter that supports lookahead in VM queues splits a received packet at an offset
     equal to or greater than the requested lookahead size and DMAs the lookahead data and the post-lookahead
     data to separate shared memory segments.

## Remarks
NDIS passes an NDIS_RESTART_GENERAL_ATTRIBUTES structure to drivers during restart operations. For
    example, when NDIS calls a miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a> function, NDIS passes a
    pointer to an 
    <a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a> structure to
    the miniport driver in the 
    <b>RestartAttributes</b> member of the 
    <a href="..\ndis\ns-ndis-_ndis_miniport_restart_parameters.md">
    NDIS_MINIPORT_RESTART_PARAMETERS</a> structure.

If the 
    <b>Oid</b> member in the NDIS_RESTART_ATTRIBUTES structure is 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
    OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>, the 
    <b>Data</b> member of NDIS_RESTART_ATTRIBUTES contains an NDIS_RESTART_GENERAL_ATTRIBUTES structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-802-3-maximum-list-size">OID_802_3_MAXIMUM_LIST_SIZE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569598">OID_GEN_MAXIMUM_FRAME_SIZE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569602">OID_GEN_MAX_LINK_SPEED</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-miniport-restart-attributes">
   OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568739">NET_IF_ACCESS_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569597">OID_GEN_MAC_OPTIONS</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-supported-packet-filters">
   OID_GEN_SUPPORTED_PACKET_FILTERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569774">OID_PNP_CAPABILITIES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_general_attributes.md">
   NDIS_MINIPORT_ADAPTER_GENERAL_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-statistics">OID_GEN_STATISTICS</a>



<a href="..\ndis\nc-ndis-miniport_restart.md">MiniportRestart</a>



<a href="..\ndis\ns-ndis-_ndis_restart_attributes.md">NDIS_RESTART_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569642">OID_GEN_SUPPORTED_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569574">OID_GEN_CURRENT_LOOKAHEAD</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568741">NET_IF_CONNECTION_TYPE</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_receive_scale_capabilities.md">
   NDIS_RECEIVE_SCALE_CAPABILITIES</a>



<a href="..\ndis\ns-ndis-_ndis_miniport_restart_parameters.md">
   NDIS_MINIPORT_RESTART_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568742">NET_IF_DIRECTION_TYPE</a>