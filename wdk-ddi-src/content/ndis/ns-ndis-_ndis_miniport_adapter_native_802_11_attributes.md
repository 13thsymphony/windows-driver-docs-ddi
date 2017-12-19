---
UID: NS.NDIS._NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
title: _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\ndis_miniport_adapter_native_802_11_attributes.htm
old-project: NetVista
ms.assetid: f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
req.alt-loc: Ndis.h
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
---

# _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct {
  NDIS_OBJECT_HEADER       Header;
  ULONG                    OpModeCapability;
  ULONG                    NumOfTXBuffers;
  ULONG                    NumOfRXBuffers;
  BOOLEAN                  MultiDomainCapabilityImplemented;
  ULONG                    NumSupportedPhys;
  PDOT11_PHY_ATTRIBUTES    SupportedPhyAttributes;
  PDOT11_EXTSTA_ATTRIBUTES ExtSTAAttributes;
#if (NDIS_SUPPORT_NDIS620)
  PDOT11_VWIFI_ATTRIBUTES  VWiFiAttributes;
  PDOT11_EXTAP_ATTRIBUTES  ExtAPAttributes;
#endif 
#if (NDIS_SUPPORT_NDIS630)
  PDOT11_WFD_ATTRIBUTES    WFDAttributes;
#endif 
} NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES;
````


## -struct-fields

### -field Header

The type, revision, and size of the NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure. This
     member is formatted as an 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES.


### -field Revision

For the Windows Vista or Windows Server 2008 operating systems, this member must be set to
        NDIS_MINIPORT_ADAPTER_802_11_ATTRIBUTES_REVISION_1.

For later versions of the Windows operating systems, this member must be set to
        NDIS_MINIPORT_ADAPTER_802_11_ATTRIBUTES_REVISION_2.


### -field Size

For the Windows Vista or Windows Server 2008 operating systems, this member must be set to
        NDIS_SIZEOF_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES_REVISION_1.

For later versions of the Windows operating systems, this member must be set to
        NDIS_SIZEOF_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES_REVISION_2.

</dd>
</dl>
For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field OpModeCapability

A bitmask of the miniport driver's supported operation modes. This bitmask is defined through the
     following:
     




### -field DOT11_OPERATION_MODE_EXTENSIBLE_AP

Specifies that the miniport driver supports the Extensible Access Point (ExtAP) operation mode.
       

This value is available beginning with Windows 7.


### -field DOT11_OPERATION_MODE_EXTENSIBLE_STATION

Specifies that the miniport driver supports the Extensible Station (ExtSTA) operation
       mode.


### -field DOT11_OPERATION_MODE_NETWORK_MONITOR

Specifies that the miniport driver supports the Network Monitor (NetMon) operation mode.

</dd>
</dl>
For more information about operation modes, see 
     <a href="netvista.native_802_11_operation_modes">Native 802.11 Operation
     Modes</a>.


### -field NumOfTXBuffers

The maximum number of media access control (MAC) service data unit (MSDU) packets that the 802.11
     station can hold in its transmit queue. The miniport driver must support a minimum transmit queue depth
     of 64.
     

The value of this member must not include the number of transmit buffers that the 802.11 station uses
     to send packets on its own, such as Beacon packets or 802.11 control packets.


### -field NumOfRXBuffers

The maximum number of MSDU packets that the 802.11 station can buffer in its receive queue. The
     miniport driver must support a minimum receive queue depth of 64.


### -field MultiDomainCapabilityImplemented

A Boolean value that, if <b>TRUE</b>, specifies that the 802.11 station can operate in multiple
     regulatory domains. For more information about 802.11 regulatory domains, refer to the IEEE 802.11d-2001
     standard.


### -field NumSupportedPhys

The number of PHYs on the 802.11 station.


### -field SupportedPhyAttributes

A pointer to an array of 
     <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structures. This
     array must have 
     <b>NumSupportedPhys</b> entries and must be sorted in the same order as the list of PHY types returned
     through a query of 
     <a href="netvista.oid_dot11_supported_phy_types">
     OID_DOT11_SUPPORTED_PHY_TYPES</a>.


### -field ExtSTAAttributes

A pointer to a 
     <a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure
     that specifies the attributes of the miniport driver and 802.11 station when operating in Extensible
     Station (ExtSTA) mode. For more information about this operation mode, see 
     <a href="netvista.extensible_station_operation_mode">Extensible Station Operation
     Mode</a>.


### -field VWiFiAttributes

A pointer to a 
      <a href="..\windot11\ns-windot11-dot11_vwifi_attributes.md">DOT11_VWIFI_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Virtual
      WiFi mode.

This member is available beginning with Windows 7.


### -field ExtAPAttributes

A pointer to a 
      <a href="netvista.dot11_extap_attributes">DOT11_EXTAP_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Extensible
      Access Point (ExtAP) mode.

This member is available beginning with Windows 7.


### -field WFDAttributes

A pointer to a 
      <a href="netvista.dot11_wfd_attributes">DOT11_WFD_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Wi-Fi Direct (WFD) mode.

This member is available beginning with Windows 8.


## -remarks
When its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function is
    called, the miniport driver must call the 
    <a href="netvista.ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function to define the Native 802.11 attributes of the driver and 802.11
    station. The miniport driver must follow these guidelines when it makes the call to 
    <b>NdisMSetMiniportAttributes</b>:

The 
      <i>MiniportAttributes</i> parameter must be set to the address of a driver-allocated block of memory
      that contains an NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure along with the ExtSTA
      attributes and an array of PHY attributes.

The 
      <b>SupportedPhyAttributes</b> member must be the address of the array of 
      <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structures. This
      array must be within the driver-allocated memory block referenced by the 
      <i>MiniportAttributes</i> parameter.

The 
      <b>ExtSTAAttributes</b> member must be the address of a 
      <a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure.
      This structure must be within the driver-allocated memory block referenced by the 
      <i>MiniportAttributes</i> parameter.

For more information about the initialization requirements for a Native 802.11 miniport driver, see 
    <a href="netvista.native_802_11_miniport_driver_initialization">Native 802.11 Miniport
    Driver Initialization</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.dot11_extap_attributes">DOT11_EXTAP_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\windot11\ns-windot11-dot11_vwifi_attributes.md">DOT11_VWIFI_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.dot11_wfd_attributes">DOT11_WFD_ATTRIBUTES</a>
</dt>
<dt>
<a href="netvista.extensible_station_operation_mode">Extensible Station Operation
   Mode</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569426">OID_DOT11_SUPPORTED_PHY_TYPES</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>
</dt>
<dt>
<a href="netvista.native_802_11_miniport_driver_initialization">Native 802.11 Miniport
   Driver Initialization</a>
</dt>
<dt>
<a href="netvista.native_802_11_operation_modes">Native 802.11 Operation Modes</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndismsetminiportattributes">NdisMSetMiniportAttributes</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

