---
UID: NS.WINDOT11._DOT11_SUPPORTED_ANTENNA_LIST
title: _DOT11_SUPPORTED_ANTENNA_LIST
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_supported_antenna_list.htm
old-project: NetVista
ms.assetid: 45c6b9a3-b834-4e57-b7f8-fab7be749269
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _DOT11_SUPPORTED_ANTENNA_LIST, *PDOT11_SUPPORTED_ANTENNA_LIST, DOT11_SUPPORTED_ANTENNA_LIST, PDOT11_SUPPORTED_ANTENNA_LIST
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_SUPPORTED_ANTENNA_LIST
req.alt-loc: windot11.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _DOT11_SUPPORTED_ANTENNA_LIST structure



## -description

## -syntax

````
typedef struct _DOT11_SUPPORTED_ANTENNA_LIST {
  ULONG                   uNumOfEntries;
  ULONG                   uTotalNumOfEntries;
  DOT11_SUPPORTED_ANTENNA dot11SupportedAntenna[1];
} DOT11_SUPPORTED_ANTENNA_LIST, *PDOT11_SUPPORTED_ANTENNA_LIST;
````


## -struct-fields

### -field uNumOfEntries

The number of entries in the 
     <b>dot11SupportedAntenna</b> array. A zero value for the 
     <b>uNumOfEntries</b> member indicates an empty list.


### -field uTotalNumOfEntries

The maximum number of entries that the 
     <b>dot11SupportedAntenna</b> array can contain.


### -field dot11SupportedAntenna

The list of supported antennas. Each element in this list is formatted as a 
     <a href="netvista.dot11_supported_antenna">
     DOT11_SUPPORTED_ANTENNA</a> structure.


## -remarks
A miniport driver returns the DOT11_SUPPORTED_ANTENNA_LIST structure when queried by either 
    <a href="netvista.oid_dot11_supported_rx_antenna">
    OID_DOT11_SUPPORTED_RX_ANTENNA</a> or 
    <a href="netvista.oid_dot11_supported_tx_antenna">
    OID_DOT11_SUPPORTED_TX_ANTENNA</a>.

When these OIDs are queried, the miniport driver must verify that the 
    <b>InformationBuffer</b> member of the 
    <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function's
    <i>OidRequest</i> parameter is large enough to return the entire DOT11_SUPPORTED_ANTENNA_LIST structure,
    including all entries in the 
    <b>dot11SupportedAntenna</b> array. The value of the 
    <b>InformationBufferLength</b> member of the 
    <i>OidRequest</i> parameter determines what the miniport driver must do, as the following list shows:

If the value of the 
      <b>InformationBufferLength</b> member is less than the length, in bytes, of the entire
      DOT11_SUPPORTED_ANTENNA_LIST structure, the miniport driver must do the following:

Set the 
        <b>uNumOfEntries</b> member to zero.

Set the 
        <b>uTotalNumOfEntries</b> member to the number of entries in the 
        <b>dot11SupportedAntenna</b> array.

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesWritten</b> member to zero and the 
        <b>BytesNeeded</b> member to the length, in bytes, of the entire DOT11_PHY_ID_LIST structure.

Fail the query request by returning NDIS_STATUS_BUFFER_OVERFLOW from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.

If the value of the 
      <b>InformationBufferLength</b> member is greater than or equal to the length, in bytes, of the entire
      DOT11_SUPPORTED_ANTENNA_LIST structure, the miniport driver must do the following to complete a
      successful query request:

For the DOT11_SUPPORTED_ANTENNA_LIST structure, set the 
        <b>uNumOfEntries</b> and 
        <b>uTotalNumOfEntries</b> members to the total number of entries in the 
        <b>dot11SupportedAntenna</b> array.

For the 
        <i>OidRequest</i> parameter, set the 
        <b>BytesNeeded</b> member to zero and the 
        <b>BytesWritten</b> member to the length, in bytes, of the entire DOT11_SUPPORTED_ANTENNA_LIST
        structure. The miniport driver must also copy the entire DOT11_SUPPORTED_ANTENNA_LIST structure to
        the 
        <b>InformationBuffer</b> member.

Return NDIS_STATUS_SUCCESS from its 
        <a href="..\ndis\nc-ndis-miniport_oid_request.md">MiniportOidRequest</a> function.


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
<dt>Windot11.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.dot11_supported_antenna">DOT11_SUPPORTED_ANTENNA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569428">OID_DOT11_SUPPORTED_RX_ANTENNA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569429">OID_DOT11_SUPPORTED_TX_ANTENNA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20DOT11_SUPPORTED_ANTENNA_LIST structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

