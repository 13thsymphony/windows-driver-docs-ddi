---
UID : NS:windot11.DOT11_DATA_RATE_MAPPING_ENTRY
title : DOT11_DATA_RATE_MAPPING_ENTRY
author : windows-driver-content
description : Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location : netvista\dot11_data_rate_mapping_entry.htm
old-project : netvista
ms.assetid : d2772a9e-655a-4e3e-8b48-65d58b0a659d
ms.author : windowsdriverdev
ms.date : 1/18/2018
ms.keywords : "*PDOT11_DATA_RATE_MAPPING_ENTRY, windot11/PDOT11_DATA_RATE_MAPPING_ENTRY, windot11/DOT11_DATA_RATE_MAPPING_ENTRY, Native_802.11_data_types_465aabe5-c790-4e3d-ae63-3313dd487eb5.xml, netvista.dot11_data_rate_mapping_entry, PDOT11_DATA_RATE_MAPPING_ENTRY, DOT11_DATA_RATE_MAPPING_ENTRY, DOT11_DATA_RATE_MAPPING_ENTRY structure [Network Drivers Starting with Windows Vista], PDOT11_DATA_RATE_MAPPING_ENTRY structure pointer [Network Drivers Starting with Windows Vista]"
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
req.typenames : "*PDOT11_DATA_RATE_MAPPING_ENTRY, DOT11_DATA_RATE_MAPPING_ENTRY"
req.product : Windows 10 or later.
---

# DOT11_DATA_RATE_MAPPING_ENTRY structure
<div class="alert"><b>Important</b>  The <a href="https://msdn.microsoft.com/library/windows/hardware/ff560689">Native 802.11 Wireless LAN</a> interface is deprecated in Windows 10 and later. Please use the WLAN Device Driver Interface (WDI) instead. For more information about WDI, see <a href="https://msdn.microsoft.com/6EF92E34-7BC9-465E-B05D-2BCB29165A18">WLAN Universal Windows driver model</a>.</div><div> </div>The DOT11_DATA_RATE_MAPPING_ENTRY structure defines a data rate supported by a PHY on the 802.11
  station for transmit and receive operations.

## Syntax
````
typedef struct DOT11_DATA_RATE_MAPPING_ENTRY {
  UCHAR  ucDataRateIndex;
  UCHAR  ucDataRateFlag;
  USHORT usDataRateValue;
} DOT11_DATA_RATE_MAPPING_ENTRY, *PDOT11_DATA_RATE_MAPPING_ENTRY;
````

## Members


`ucDataRateFlag`

The attributes of the data rate entry.
     

This value is a bitmask as defined in the following table.
<table>
<tr>
<th>Bits</th>
<th>Name</th>
<th>Description</th>
</tr>
<tr>
<td>
0

</td>
<td>
<b>DOT11_DATA_RATE_NON_STANDARD</b>

</td>
<td>
If set, the entry is not a standard data rate defined in IEEE 802.11 standards.

</td>
</tr>
<tr>
<td>
1-7

</td>
<td></td>
<td>
These bits are not used and must be set to zero.

</td>
</tr>
</table>

`ucDataRateIndex`

The index value for the data rate contained in the 
     <b>usDataRateValue</b> member. The value of the 
     <b>ucDataRateIndex</b> member must be unique for each entry in the 
     <b>DataRateMappingEntries</b> array.
     

This value is a bitmask as defined in the following table.
<table>
<tr>
<th>Bits</th>
<th>Description</th>
</tr>
<tr>
<td>
0-6

</td>
<td>
The data rate index, containing a value from 2 through127.

</td>
</tr>
<tr>
<td>
7

</td>
<td>
This bit is not used and must be set to zero.

</td>
</tr>
</table>

`usDataRateValue`

The data rate, defined in units of 500 kilobits per second (Kbps), with a value from 0x0002 to
     0xFFFF.

## Remarks
For the IEEE 802.11 standard data rates, the miniport driver must set the 
    <b>ucDataRateIndex</b> and 
    <b>usDataRateValue</b> members to the same value.

The following table shows the IEEE 802.11 standard data rates, in units of megabits per second (Mbps),
    and the related values for the 
    <b>ucDataRateIndex</b> and 
    <b>usDataRateValue</b> members.
<table>
<tr>
<th>IEEE 802.11 Standard Rate</th>
<th>ucDataRateIndex</th>
<th>usDataRateValue</th>
</tr>
<tr>
<td>
1 Mbps

</td>
<td>
0x02

</td>
<td>
0x02

</td>
</tr>
<tr>
<td>
2 Mbps

</td>
<td>
0x04

</td>
<td>
0x04

</td>
</tr>
<tr>
<td>
3 Mbps

</td>
<td>
0x06

</td>
<td>
0x06

</td>
</tr>
<tr>
<td>
4.5 Mbps

</td>
<td>
0x09

</td>
<td>
0x09

</td>
</tr>
<tr>
<td>
5.5 Mbps

</td>
<td>
0x0B

</td>
<td>
0x0B

</td>
</tr>
<tr>
<td>
6 Mbps

</td>
<td>
0x0C

</td>
<td>
0x0C

</td>
</tr>
<tr>
<td>
9 Mbps

</td>
<td>
0x12

</td>
<td>
0x12

</td>
</tr>
<tr>
<td>
11 Mbps

</td>
<td>
0x16

</td>
<td>
0x16

</td>
</tr>
<tr>
<td>
12 Mbps

</td>
<td>
0x18

</td>
<td>
0x18

</td>
</tr>
<tr>
<td>
18 Mbps

</td>
<td>
0x24

</td>
<td>
0x24

</td>
</tr>
<tr>
<td>
22 Mbps

</td>
<td>
0x2C

</td>
<td>
0x2C

</td>
</tr>
<tr>
<td>
24 Mbps

</td>
<td>
0x30

</td>
<td>
0x30

</td>
</tr>
<tr>
<td>
27 Mbps

</td>
<td>
0x36

</td>
<td>
0x36

</td>
</tr>
<tr>
<td>
33 Mbps

</td>
<td>
0x42

</td>
<td>
0x42

</td>
</tr>
<tr>
<td>
36 Mbps

</td>
<td>
0x48

</td>
<td>
0x48

</td>
</tr>
<tr>
<td>
48 Mbps

</td>
<td>
0x60

</td>
<td>
0x60

</td>
</tr>
<tr>
<td>
54 Mbps

</td>
<td>
0x6C

</td>
<td>
0x6C

</td>
</tr>
</table>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | windot11.h (include Ndis.h) |

## See Also

<a href="..\windot11\ns-windot11-dot11_phy_attributes.md">DOT11_PHY_ATTRIBUTES</a>

<mshelp:link keywords="netvista.oid_dot11_data_rate_mapping_table" tabindex="0">
   OID_DOT11_DATA_RATE_MAPPING_TABLE</mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_DATA_RATE_MAPPING_ENTRY structure%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>