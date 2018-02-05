---
UID : NS:windot11.DOT11_PHY_ATTRIBUTES
title : DOT11_PHY_ATTRIBUTES
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11_phy_attributes.htm
old-project : netvista
ms.assetid : 9e81144e-e562-4f61-83de-7b7659106de8
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : DOT11_PHY_ATTRIBUTES structure [Network Drivers Starting with Windows Vista], windot11/DOT11_PHY_ATTRIBUTES, *PDOT11_PHY_ATTRIBUTES, netvista.dot11_phy_attributes, windot11/PDOT11_PHY_ATTRIBUTES, PDOT11_PHY_ATTRIBUTES structure pointer [Network Drivers Starting with Windows Vista], Native_802.11_data_types_76ba44f0-4597-4397-b686-1f70e5e27eec.xml, PDOT11_PHY_ATTRIBUTES, DOT11_PHY_ATTRIBUTES
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : struct
req.header : windot11.h
req.include-header : Ndis.h
req.target-type : Windows
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating   systems.
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
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PDOT11_PHY_ATTRIBUTES, DOT11_PHY_ATTRIBUTES"
req.product : Windows 10 or later.
---

# DOT11_PHY_ATTRIBUTES structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_PHY_ATTRIBUTES structure defines the physical and operating attributes of a PHY on the
  802.11 station.

## Syntax
````
typedef struct DOT11_PHY_ATTRIBUTES {
  NDIS_OBJECT_HEADER                  Header;
  DOT11_PHY_TYPE                      PhyType;
  BOOLEAN                             bHardwarePhyState;
  BOOLEAN                             bSoftwarePhyState;
  BOOLEAN                             bCFPollable;
  ULONG                               uMPDUMaxLength;
  DOT11_TEMP_TYPE                     TempType;
  DOT11_DIVERSITY_SUPPORT             DiversitySupport;
  union {
    DOT11_HRDSSS_PHY_ATTRIBUTES HRDSSSAttributes;
    DOT11_OFDM_PHY_ATTRIBUTES   OFDMAttributes;
    DOT11_ERP_PHY_ATTRIBUTES    ERPAttributes;
  };
  ULONG                               uNumberSupportedPowerLevels;
  ULONG                               TxPowerLevels[8];
  ULONG                               uNumDataRateMappingEntries;
  DOT11_DATA_RATE_MAPPING_ENTRY       DataRateMappingEntries[DOT11_RATE_SET_MAX_LENGTH];
  DOT11_SUPPORTED_DATA_RATES_VALUE_V2 SupportedDataRatesValue;
} DOT11_PHY_ATTRIBUTES, *PDOT11_PHY_ATTRIBUTES;
````

## Members


`bCFPollable`

A Boolean value that, if set to <b>TRUE</b>, indicates that the 802.11 station supports CF-Poll frames. For
      more information about CF-Poll frames, refer to Clause 9.4 of the IEEE 802.11-2012 standard.

This member is not applicable to the Extensible Access Point (ExtAP) operation mode and is ignored
      when the NIC is in the ExtAP mode.

`bHardwarePhyState`

A Boolean value that specifies the hardware power state of the PHY. If <b>TRUE</b>, the hardware power
      state is enabled. If <b>FALSE</b>, the hardware power state is disabled.

For more information about the PHY's hardware power state, see 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-hardware-phy-state">
      OID_DOT11_HARDWARE_PHY_STATE</a>.
<div class="alert"><b>Note</b>  Whenever the PHY's hardware power state changes, the miniport driver must make an 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-phy-state-changed">
      NDIS_STATUS_DOT11_PHY_STATE_CHANGED</a> media-specific status indication.</div><div> </div>

`bSoftwarePhyState`

A Boolean value that specifies the software power state of the PHY. If <b>TRUE</b>, the software power
      state is enabled. If <b>FALSE</b>, the software power state is disabled.

For more information about the PHY's software power state, see 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569392">OID_DOT11_NIC_POWER_STATE</a>.
<div class="alert"><b>Note</b>  Whenever the PHY's software power state changes, the miniport driver must make an 
      <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/ndis-status-dot11-phy-state-changed">
      NDIS_STATUS_DOT11_PHY_STATE_CHANGED</a> media-specific status indication.</div><div> </div>

`DiversitySupport`

The PHY's type of antenna diversity, defined through a 
      <a href="..\windot11\ne-windot11-_dot11_diversity_support.md">DOT11_DIVERSITY_SUPPORT</a> enumeration
      value.

`Header`

The type, revision, and size of the DOT11_PHY_ATTRIBUTES structure. This member is formatted as an 
      <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.

The miniport driver must set the members of 
      <b>Header</b> to the following values:



For more information about these members, see 
      <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


#### Revision

This member must be set to DOT11_PHY_ATTRIBUTES_REVISION_1.


#### Size

This member must be set to 
        sizeof(DOT11_PHY_ATTRIBUTES).


#### Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.

`PhySpecificAttributes`



`PhyType`

The type of the PHY as specified by a 
     <a href="..\windot11\ne-windot11-_dot11_phy_type.md">DOT11_PHY_TYPE</a> enumerator value.

`TempType`

The PHY's operating temperature range, defined through a 
      <a href="..\windot11\ne-windot11-_dot11_temp_type.md">DOT11_TEMP_TYPE</a> enumeration value.

`uMPDUMaxLength`

The maximum length, in bytes, of a media access control (MAC) protocol data unit (MPDU) frame that
      the PHY can transmit or receive. For more information, see 
      <a href="https://msdn.microsoft.com/library/windows/hardware/ff569387">OID_DOT11_MPDU_MAX_LENGTH</a>.
<div class="alert"><b>Note</b>  Whenever the PHY's software power state changes, the miniport driver must make an
      NDIS_STATUS_DOT11_MPDU_MAX_LENGTH_CHANGED media-specific status indication.</div><div> </div>

## Remarks
The 
    <a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a> structure contains a member (<b>pExtPhyAttributes</b>) that specifies the address of an array of DOT11_PHY_ATTRIBUTES structures. When
    the miniport driver calls 
    <a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>,
    the driver sets the 
    <i>MiniportAttributes</i> parameter to the address of driver-allocated block of memory which contains an
    NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES structure along with the array of DOT11_PHY_ATTRIBUTES
    structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | windot11.h (include Ndis.h) |

## See Also

<a href="..\windot11\ns-windot11-dot11_data_rate_mapping_entry.md">DOT11_DATA_RATE_MAPPING_ENTRY</a>

<a href="..\windot11\ne-windot11-_dot11_phy_type.md">DOT11_PHY_TYPE</a>

<a href="..\windot11\ne-windot11-_dot11_diversity_support.md">DOT11_DIVERSITY_SUPPORT</a>

<a href="..\windot11\ne-windot11-_dot11_temp_type.md">DOT11_TEMP_TYPE</a>

<a href="..\windot11\ns-windot11-_dot11_supported_data_rates_value_v2.md">
   DOT11_SUPPORTED_DATA_RATES_VALUE_V2</a>

<a href="..\windot11\ns-windot11-dot11_ofdm_phy_attributes.md">DOT11_OFDM_PHY_ATTRIBUTES</a>

<a href="..\ndis\ns-ndis-_ndis_miniport_adapter_native_802_11_attributes.md">
   NDIS_MINIPORT_ADAPTER_NATIVE_802_11_ATTRIBUTES</a>

<a href="..\ndis\nf-ndis-ndismsetminiportattributes.md">NdisMSetMiniportAttributes</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff569392">OID_DOT11_NIC_POWER_STATE</a>

<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/oid-dot11-hardware-phy-state">OID_DOT11_HARDWARE_PHY_STATE</a>

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>

<a href="..\windot11\ns-windot11-dot11_hrdsss_phy_attributes.md">DOT11_HRDSSS_PHY_ATTRIBUTES</a>

<a href="..\windot11\ns-windot11-dot11_erp_phy_attributes.md">DOT11_ERP_PHY_ATTRIBUTES</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_PHY_ATTRIBUTES structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>