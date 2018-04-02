---
UID: NS:ndis._NDIS_FILTER_ATTACH_PARAMETERS
title: "_NDIS_FILTER_ATTACH_PARAMETERS"
author: windows-driver-content
description: The NDIS_FILTER_ATTACH_PARAMETERS structure defines the initialization parameters for the filter module.
old-location: netvista\ndis_filter_attach_parameters.htm
old-project: netvista
ms.assetid: d46a1e62-9d03-4ab9-86f6-81b06c04d0f6
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_FILTER_ATTACH_PARAMETERS, NDIS_FILTER_ATTACH_PARAMETERS, NDIS_FILTER_ATTACH_PARAMETERS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_ATTACH_PARAMETERS, PNDIS_FILTER_ATTACH_PARAMETERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_ATTACH_PARAMETERS, filter_structures_ref_3ab66eda-29e5-4442-9506-6e51238cec5f.xml, ndis/NDIS_FILTER_ATTACH_PARAMETERS, ndis/PNDIS_FILTER_ATTACH_PARAMETERS, netvista.ndis_filter_attach_parameters"
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
-	NDIS_FILTER_ATTACH_PARAMETERS
product: Windows
targetos: Windows
req.typenames: NDIS_FILTER_ATTACH_PARAMETERS, *PNDIS_FILTER_ATTACH_PARAMETERS
---

# _NDIS_FILTER_ATTACH_PARAMETERS structure
The <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure defines the initialization parameters for the filter
  module.

## Syntax
```
typedef struct _NDIS_FILTER_ATTACH_PARAMETERS {
  NDIS_OBJECT_HEADER                Header;
  NET_IFINDEX                       IfIndex;
  NET_LUID                          NetLuid;
  PNDIS_STRING                      FilterModuleGuidName;
  NET_IFINDEX                       BaseMiniportIfIndex;
  PNDIS_STRING                      BaseMiniportInstanceName;
  PNDIS_STRING                      BaseMiniportName;
  NDIS_MEDIA_CONNECT_STATE          MediaConnectState;
  NET_IF_MEDIA_DUPLEX_STATE         MediaDuplexState;
  ULONG64                           XmitLinkSpeed;
  ULONG64                           RcvLinkSpeed;
  NDIS_MEDIUM                       MiniportMediaType;
  NDIS_PHYSICAL_MEDIUM              MiniportPhysicalMediaType;
  NDIS_HANDLE                       MiniportMediaSpecificAttributes;
  PNDIS_OFFLOAD                     DefaultOffloadConfiguration;
  USHORT                            MacAddressLength;
  UCHAR                             CurrentMacAddress[NDIS_MAX_PHYS_ADDRESS_LENGTH];
  NET_LUID                          BaseMiniportNetLuid;
  NET_IFINDEX                       LowerIfIndex;
  NET_LUID                          LowerIfNetLuid;
  ULONG                             Flags;
  PNDIS_HD_SPLIT_CURRENT_CONFIG     HDSplitCurrentConfig;
  PNDIS_RECEIVE_FILTER_CAPABILITIES ReceiveFilterCapabilities;
  PDEVICE_OBJECT                    MiniportPhysicalDeviceObject;
  PNDIS_NIC_SWITCH_CAPABILITIES     NicSwitchCapabilities;
  BOOLEAN                           BaseMiniportIfConnectorPresent;
  PNDIS_SRIOV_CAPABILITIES          SriovCapabilities;
  PNDIS_NIC_SWITCH_INFO_ARRAY       NicSwitchArray;
} *PNDIS_FILTER_ATTACH_PARAMETERS, NDIS_FILTER_ATTACH_PARAMETERS;
```

## Members


`Header`

The 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure for the
     <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure. NDIS sets the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_ATTACH_PARAMETERS.
     

To indicate the version of the <b>NDIS_FILTER_ATTACH_PARAMETERS</b> structure, NDIS sets the 
     <b>Revision</b> member to one of the following values:





#### NDIS_FILTER_ATTACH__PARAMETERS_REVISION_4

Added various members for NDIS 6.30.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_4.



#### NDIS_FILTER_ATTACH_PARAMETERS_REVISION_3

Added the 
        <b>ReceiveFilterCapabilities</b>, 
        <b>MiniportPhysicalDeviceObject</b>, and 
        <b>NicSwitchCapabilities</b> members for NDIS 6.20.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_3.



#### NDIS_FILTER_ATTACH_PARAMETERS_REVISION_2

Added the 
        <b>HDSplitCurrentConfig</b> member for NDIS 6.1.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_2.



#### NDIS_FILTER_ATTACH_PARAMETERS_REVISION_1

Original version for NDIS 6.0.

NDIS sets the 
        <b>Size</b> member to NDIS_SIZEOF_FILTER_ATTACH_PARAMETERS_REVISION_1.

`IfIndex`

The NDIS interface index of the filter module that NDIS is attaching to the driver stack.

`NetLuid`

The NDIS network interface 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> value for the filter module that NDIS is
     attaching to the driver stack. The NET_LUID is equivalent to the interface name (<i>ifName</i> in RFC 2863
     <i>)</i>.

`FilterModuleGuidName`

The GUID name of the filter module that NDIS is attaching.

`BaseMiniportIfIndex`

The NDIS network interface index of the base miniport adapter. That is, if there are virtual
     miniports or filter modules that are installed over a physical miniport adapter, the value of this
     member is the interface index of the physical miniport adapter or a virtual miniport of the highest-level MUX intermediate driver.

`BaseMiniportInstanceName`

A pointer to an NDIS_STRING type value that contains a counted Unicode string. This string
     specifies the friendly name of the interface for the base miniport adapter. For Windows 2000 and later
     versions, NDIS defines the NDIS_STRING type as a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a> type.

`BaseMiniportName`

The name of the base miniport adapter.

`MediaConnectState`

The 
     <a href="https://msdn.microsoft.com/5af5e050-4b2b-45a9-8549-3a3818d7b06f">
     NET_IF_MEDIA_CONNECT_STATE</a> connection state type.

`MediaDuplexState`

The media duplex state for the underlying miniport adapter. For more information, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-duplex-state">OID_GEN_MEDIA_DUPLEX_STATE</a>.

`XmitLinkSpeed`

The current transmit link speed of the underlying miniport adapter in bits per second. For more
     information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.

`RcvLinkSpeed`

The current receive link speed of the underlying miniport adapter in bits per second. For more
     information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>.

`MiniportMediaType`

The 
     <b>NdisMedium</b><i>Xxx</i> type that the base underlying miniport adapter supports. For more
     information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>.

`MiniportPhysicalMediaType`

The physical medium type for the base underlying miniport adapter. For more information, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>.

`MiniportMediaSpecificAttributes`

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure that
     identifies a structure that contains miniport media-specific attributes, or <b>NULL</b> if there are no such
     attributes. The 
     <b>Type</b> member of the NDIS_OBJECT_HEADER structure identifies the type of the
     attributes structure. For example, if the underlying miniport adapter's media type is 
     <b>NdisMediumNative802_11</b>, then the 
     <b>Type</b> member should be
     NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, and the 
     <b>MiniportMediaSpecificAttributes</b> member points to an 
     <a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
     NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure.

`DefaultOffloadConfiguration`

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a> structure which defines task
     offload attributes. The filter driver should review these attributes to obtain the task offload
     capabilities of the underlying drivers. The filter driver should modify these attributes, if necessary,
     to reflect any changes in the task offload support that it requires.

`MacAddressLength`

The MAC address length, in bytes. The MAC address length is specific to the type of media.

`CurrentMacAddress`

The current MAC address. For example, the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a> OID
     specifies the current MAC address for IEEE 802.3 drivers.

`BaseMiniportNetLuid`

The NDIS network interface 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a> of the base miniport adapter. That is, if
     there are virtual miniports or filter modules that are installed over a physical miniport adapter, the
     value of this member is the NET_LUID of the physical miniport adapter or a virtual miniport of the
     highest-level MUX intermediate driver.

`LowerIfIndex`

The NDIS network interface index of the interface just below the current filter module. That is,
     if there are filter modules or NDIS 5.
     <i>x</i> filter intermediate drivers that are installed over a physical miniport
     adapter or the highest-level MUX intermediate driver, this member contains the interface index of the
     filter module interface or filter intermediate driver interface that is just below the current filter
     module. If there are no filter module or filter intermediate driver interfaces installed over the
     physical miniport adapter or the highest-level MUX intermediate driver, this member contains the
     interface index of the underlying physical miniport adapter or the highest-level MUX intermediate driver
     virtual miniport.

`LowerIfNetLuid`

The NDIS network interface NET_LUID value of the interface just below the current filter module.
     That is, if there are filter modules or NDIS 5.
     <i>x</i> filter intermediate drivers that are installed over a physical miniport
     adapter or the highest-level MUX intermediate driver, this member contains the network interface
     NET_LUID of the filter module interface or filter intermediate driver interface that is just below the
     current filter module. If there are no filter module or filter intermediate driver interfaces installed
     over the physical miniport adapter or the highest-level MUX intermediate driver, this member contains
     the network interface NET_LUID of the underlying physical miniport adapter or the highest-level MUX
     intermediate driver virtual miniport.

`Flags`

Reserved for future use.

`HDSplitCurrentConfig`

A pointer to an 
     <a href="https://msdn.microsoft.com/866fe9e6-0cb1-45cd-84b4-4e2df9c9c45a">
     NDIS_HD_SPLIT_CURRENT_CONFIG</a> structure. This structure specifies the current header-data split
     configuration of the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does
     not support header-data split.

`ReceiveFilterCapabilities`

A pointer to an 
     <a href="https://msdn.microsoft.com/aecc1fe0-03f9-44be-9a38-b689eee4c5a6">
     NDIS_RECEIVE_FILTER_CAPABILITIES</a> structure. This structure specifies the generic filtering
     capabilities that are currently enabled on the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not
     support receive filtering.

`MiniportPhysicalDeviceObject`

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a> structure. This structure
     represents the physical device for the underlying miniport adapter.

`NicSwitchCapabilities`

A pointer to an 
     <a href="https://msdn.microsoft.com/bc4b56bd-583f-4b41-b5a7-90958ce65f42">
     NDIS_NIC_SWITCH_CAPABILITIES</a> structure. This structure specifies the NIC switch capabilities of
     the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not support NIC
     switch features.

`BaseMiniportIfConnectorPresent`

A Boolean value that, if set to TRUE, indicates whether a network interface (if) connector is present on the underlying network adapter. This value should be set to TRUE for a physical adapter.

`SriovCapabilities`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451677">NDIS_SRIOV_CAPABILITIES</a> structure. This structure specifies the single root I/O virtualization (SR-IOV) capabilities that are currently enabled on the underlying miniport adapter. This value can be <b>NULL</b> if the miniport adapter does not support SR-IOV features.

For more information, see <a href="https://msdn.microsoft.com/E64DD4F0-D5F8-4FFF-931B-C04C5C42D000">Single Root I/O Virtualization (SR-IOV)</a>.

`NicSwitchArray`

A pointer to an <a href="https://msdn.microsoft.com/library/windows/hardware/hh451584">NDIS_NIC_SWITCH_INFO_ARRAY</a> structure.  This array enumerates the NIC switches that have been created on the miniport adapter. NIC switches can be created only if SR-IOV is supported and enabled on the adapter. 

<div class="alert"><b>Note</b>  Starting with Windows Server 2012, Windows supports only the default NIC switch that is created on the physical function (PF) miniport adapter. Therefore, this array can contain only one element. </div>
<div> </div>

## Remarks
To define filter module attach parameters, NDIS passes a pointer to an NDIS_FILTER_ATTACH_PARAMETERS
    structure to the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a> function.

Filter drivers should avoid issuing unnecessary OID queries. Instead, use the information in
    NDIS_FILTER_ATTACH_PARAMETERS, when available, to obtain information about underlying drivers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543147">DEVICE_OBJECT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540442">FilterAttach</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565696">NDIS_HD_SPLIT_CURRENT_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff565910">NDIS_MEDIUM</a>



<a href="https://msdn.microsoft.com/f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566583">NDIS_NIC_SWITCH_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451584">NDIS_NIC_SWITCH_INFO_ARRAY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff566599">NDIS_OFFLOAD</a>



<a href="https://msdn.microsoft.com/aecc1fe0-03f9-44be-9a38-b689eee4c5a6">
   NDIS_RECEIVE_FILTER_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451677">NDIS_SRIOV_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568744">NET_IF_MEDIA_CONNECT_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568747">NET_LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569069">OID_802_3_CURRENT_ADDRESS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569594">OID_GEN_LINK_SPEED_EX</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-connect-status-ex">OID_GEN_MEDIA_CONNECT_STATUS_EX</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-gen-media-duplex-state">OID_GEN_MEDIA_DUPLEX_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff569621">OID_GEN_PHYSICAL_MEDIUM</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564879">UNICODE_STRING</a>