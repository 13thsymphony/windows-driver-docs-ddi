---
UID: NS:ndis._NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
title: "_NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES"
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\ndis_miniport_adapter_native_802_11_attributes.htm
old-project: netvista
ms.assetid: f841c7f9-9ad3-4b53-b2d9-0d66d6e64b8b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], Native_802.11_data_types_7b3396ce-7830-4b08-8df4-e0d8f49c7144.xml, PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, ndis/NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, ndis/PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, netvista.ndis_miniport_adapter_native_802_11_attributes"
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
-	Ndis.h
api_name:
-	NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
product: Windows
targetos: Windows
req.typenames: NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES, *PNDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES
---

# _NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure defines the physical and operating
  attributes of the Native 802.11 miniport driver and 802.11 station.

## Syntax
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

## Members


`ExtAPAttributes`

A pointer to a 
      <a href="..\windot11\ns-windot11-_dot11_extap_attributes.md">DOT11_EXTAP_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Extensible
      Access Point (ExtAP) mode.

This member is available beginning with Windows 7.

`ExtSTAAttributes`

A pointer to a 
     <a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure
     that specifies the attributes of the miniport driver and 802.11 station when operating in Extensible
     Station (ExtSTA) mode. For more information about this operation mode, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/extensible-station-operation-mode">Extensible Station Operation
     Mode</a>.

`Header`

The type, revision, and size of the NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure. This
     member is formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:





#### Type

This member must be set to NDIS_OBJECT_TYPE_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES.



#### Revision

For the Windows Vista or Windows Server 2008 operating systems, this member must be set to
        NDIS_MINIPORT_ADAPTER_802_11_ATTRIBUTES_REVISION_1.

For later versions of the Windows operating systems, this member must be set to
        NDIS_MINIPORT_ADAPTER_802_11_ATTRIBUTES_REVISION_2.



#### Size

For the Windows Vista or Windows Server 2008 operating systems, this member must be set to
        NDIS_SIZEOF_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES_REVISION_1.

For later versions of the Windows operating systems, this member must be set to
        NDIS_SIZEOF_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES_REVISION_2.

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.

`MultiDomainCapabilityImplemented`

A Boolean value that, if <b>TRUE</b>, specifies that the 802.11 station can operate in multiple
     regulatory domains. For more information about 802.11 regulatory domains, refer to the IEEE 802.11d-2001
     standard.

`NumOfRXBuffers`

The maximum number of MSDU packets that the 802.11 station can buffer in its receive queue. The
     miniport driver must support a minimum receive queue depth of 64.

`NumOfTXBuffers`

The maximum number of media access control (MAC) service data unit (MSDU) packets that the 802.11
     station can hold in its transmit queue. The miniport driver must support a minimum transmit queue depth
     of 64.
     

The value of this member must not include the number of transmit buffers that the 802.11 station uses
     to send packets on its own, such as Beacon packets or 802.11 control packets.

`NumSupportedPhys`

The number of PHYs on the 802.11 station.

`OpModeCapability`

A bitmask of the miniport driver's supported operation modes. This bitmask is defined through the
     following:
     





#### DOT11_OPERATION_MODE_EXTENSIBLE_AP

Specifies that the miniport driver supports the Extensible Access Point (ExtAP) operation mode.
       

This value is available beginning with Windows 7.



#### DOT11_OPERATION_MODE_EXTENSIBLE_STATION

Specifies that the miniport driver supports the Extensible Station (ExtSTA) operation
       mode.



#### DOT11_OPERATION_MODE_NETWORK_MONITOR

Specifies that the miniport driver supports the Network Monitor (NetMon) operation mode.

For more information about operation modes, see 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation
     Modes</a>.

`SupportedPhyAttributes`

A pointer to an array of 
     <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structures. This
     array must have 
     <b>NumSupportedPhys</b> entries and must be sorted in the same order as the list of PHY types returned
     through a query of 
     <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-phy-types">
     OID_DOT11_SUPPORTED_PHY_TYPES</a>.

`VWiFiAttributes`

A pointer to a 
      <a href="..\windot11\ns-windot11-dot11_vwifi_attributes.md">DOT11_VWIFI_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Virtual
      WiFi mode.

This member is available beginning with Windows 7.

`WFDAttributes`

A pointer to a 
      <a href="..\windot11\ns-windot11-_dot11_wfd_attributes.md">DOT11_WFD_ATTRIBUTES</a> structure
      that specifies the attributes of the miniport driver and 802.11 station when it operates in Wi-Fi Direct (WFD) mode.

This member is available beginning with Windows 8.

## Remarks
When its 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function is
    called, the miniport driver must call the 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">
    NdisMSetMiniportAttributes</a> function to define the Native 802.11 attributes of the driver and 802.11
    station. The miniport driver must follow these guidelines when it makes the call to 
    <b>NdisMSetMiniportAttributes</b>:

<ul>
<li>
The 
      <i>MiniportAttributes</i> parameter must be set to the address of a driver-allocated block of memory
      that contains an NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure along with the ExtSTA
      attributes and an array of PHY attributes.

</li>
<li>
The 
      <b>SupportedPhyAttributes</b> member must be the address of the array of 
      <a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a> structures. This
      array must be within the driver-allocated memory block referenced by the 
      <i>MiniportAttributes</i> parameter.

</li>
<li>
The 
      <b>ExtSTAAttributes</b> member must be the address of a 
      <a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a> structure.
      This structure must be within the driver-allocated memory block referenced by the 
      <i>MiniportAttributes</i> parameter.

</li>
</ul>
For more information about the initialization requirements for a Native 802.11 miniport driver, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-miniport-drivers2">Native 802.11 Miniport
    Driver Initialization</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | ndis.h |

## See Also

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/extensible-station-operation-mode">Extensible Station Operation
   Mode</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-operation-modes">Native 802.11 Operation Modes</a>



<a href="..\windot11\ns-windot11-_dot11_extap_attributes.md">DOT11_EXTAP_ATTRIBUTES</a>



<a href="..\windot11\ns-windot11-dot11_extsta_attributes.md">DOT11_EXTSTA_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-supported-phy-types">OID_DOT11_SUPPORTED_PHY_TYPES</a>



<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/native-802-11-miniport-drivers2">Native 802.11 Miniport
   Driver Initialization</a>



<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>



<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\windot11\ns-windot11-_dot11_wfd_attributes.md">DOT11_WFD_ATTRIBUTES</a>



<a href="..\windot11\ns-windot11-dot11_vwifi_attributes.md">DOT11_VWIFI_ATTRIBUTES</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>