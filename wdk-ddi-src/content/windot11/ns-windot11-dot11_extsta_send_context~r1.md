---
UID: NS.WINDOT11.DOT11_EXTSTA_SEND_CONTEXT~R1
title: DOT11_EXTSTA_SEND_CONTEXT
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_extsta_send_context.htm
old-project: netvista
ms.assetid: 0a4af7dc-0210-42b6-b15b-a0f885664da9
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: DOT11_EXTSTA_SEND_CONTEXT, DOT11_EXTSTA_SEND_CONTEXT, *PDOT11_EXTSTA_SEND_CONTEXT, DOT11_EXTAP_SEND_CONTEXT, *PDOT11_EXTAP_SEND_CONTEXT
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
req.alt-api: DOT11_EXTSTA_SEND_CONTEXT
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

# DOT11_EXTSTA_SEND_CONTEXT structure



## -description

## -syntax

````
typedef struct DOT11_EXTSTA_SEND_CONTEXT {
  NDIS_OBJECT_HEADER Header;
  USHORT             usExemptionActionType;
  ULONG              uPhyId;
  ULONG              uDelayedSleepValue;
  PVOID              pvMediaSpecificInfo;
  ULONG              uSendFlags;
} DOT11_EXTSTA_SEND_CONTEXT, *PDOT11_EXTSTA_SEND_CONTEXT;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_EXTSTA_SEND_CONTEXT structure. This member is formatted
     as an 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:




### -field Type

This member must be set to NDIS_OBJECT_TYPE_DEFAULT.


### -field Revision

This member must be set to DOT11_EXTSTA_SEND_CONTEXT_REVISION_1.


### -field Size

This member must be set to 
       sizeof(DOT11_EXTSTA_SEND_CONTEXT).

</dd>
</dl>
For more information about these members, see 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>.


### -field usExemptionActionType

The type of encryption exemption for the packet. The following exemption types are defined:
     




### -field DOT11_EXEMPT_NO_EXEMPTION

The packet is not exempt from any cipher operations performed by the 802.11 station.


### -field DOT11_EXEMPT_ALWAYS

The packet is exempt from any cipher operations performed by the 802.11 station. The 802.11
       station must transmit the packet unencrypted.


### -field DOT11_EXEMPT_ON_KEY_MAPPING_KEY_UNAVAILABLE

The packet is exempt from any cipher operations performed by the 802.11 station only if the
       station does not have a key-mapping key for the packet's destination media access control (MAC)
       address. For more information about key-mapping keys, see 
       <a href="netvista.802_11_cipher_key_types">802.11 Cipher Key Types</a>.

</dd>
</dl>

### -field uPhyId

The identifier (ID) of a PHY type on the 802.11 station. The 802.11 station must use the specified
     PHY to transmit the packet.
     

The value of 
     <b>uPhyId</b> must be one of the following:

<ul>
<li>
The value of an entry in the list of active PHY types defined by the 
       <b>msDot11ActivePhyList</b> MIB object. The miniport driver sets this MIB object to the list of PHYs
       that have been activated for use over the current basic service set (BSS) network connection. For more
       information about the 
       <b>msDot11ActivePhyList</b> MIB object, see 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff569102">OID_DOT11_ACTIVE_PHY_LIST</a>.

</li>
<li>
The value of DOT11_PHY_ID_ANY, in which case the 802.11 station can use any PHY from the list of
       active PHYs defined by the 
       <b>msDot11ActivePhyList</b> MIB object.

</li>
</ul>
The miniport driver must fail the send request if the PHY specified by 
     <b>uPhyId</b> is either not supported or has been disabled through a proprietary mechanism implemented by
     the independent hardware vendor (IHV). In this situation, the miniport driver sets the 
     <b>Status</b> member of the 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure to
     NDIS_STATUS_UNSUPPORTED_MEDIA and calls 
     <a href="netvista.ndismsendnetbufferlistscomplete">
     NdisMSendNetBufferListsComplete</a> to complete the send request.


### -field uDelayedSleepValue

The time, in microseconds, before a response to the packet is expected. The 
     <b>uDelayedSleepValue</b> member is only valid when all of the following are true:
     

<ul>
<li>
The packet is a media access control (MAC) service data unit (MSDU) packet.

</li>
<li>
The 802.11 station is operating in a power save (PS) mode. In this situation, the Extensible
       Station (ExtSTA) 
       <b>msDot11PowerSavingLevel</b> management information base (MIB) object has any value except
       DOT11_POWER_SAVING_NO_POWER_SAVING. For more information about the 
       <b>msDot11PowerSavingLevel</b> MIB value, see 
       <a href="netvista.oid_dot11_power_mgmt_request">
       OID_DOT11_POWER_MGMT_REQUEST</a>.

</li>
</ul>
The 802.11 station uses the value of 
     <b>uDelayedSleepValue</b> to optimize network performance while operating in a PS mode. For example,
     depending upon the PS mode, the 802.11 station might keep the radio turned on after the transmission of
     the packet if 
     <b>uDelayedSleepValue</b> is small. By doing so, the network latency will be reduced for receiving the
     response.


### -field pvMediaSpecificInfo

A pointer to a buffer that contains media-specific information. This member should be <b>NULL</b> when
     the 802.11 
     <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure that this
     structure is associated with comes from the native 802.11 framework itself (including any
     NET_BUFFER_LIST structures that come from an IHV extension).
     

Otherwise, 
     <b>pvMediaSpecificInfo</b> points to the out-of-band (OOB) data that is associated with the 
     <b>MediaSpecificInformation</b> entry at the 
     <b>NetBufferListInfo</b> member of the original 802.3 NET_BUFFER_LIST structure. 
     <b>pvMediaSpecificInfo</b> allows the miniport driver to access the media-specific information from an
     IHV-specific 802.3 protocol driver.


### -field uSendFlags

A set of flags that define send attributes. Currently, there are no flags defined. This member
     should be zero.


## -remarks
The miniport driver performs a send operation when its 
    <a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">
    MiniportSendNetBufferLists</a> is called. Each packet passed to the driver through this function is
    defined by a 
    <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure, which contains
    Native 802.11 out-of-band (OOB) data. The OOB data contains media-specific parameters that the 802.11
    station uses when transmitting the packet.

The miniport driver accesses the Native 802.11 OOB data through the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro with the
    following parameters:

The 
      <i>_NBL</i> parameter, which is passed the pointer to the 
      <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> structure used for the
      received 802.11 packet.

The _
      <i>id</i> parameter, which is passed the identifier (ID) value of 
      <b>MediaSpecificInformation</b>.

For more information about Native 802.11 send operations, see 
    <a href="netvista.native_802_11_send_operations">Native 802.11 Send
    Operations</a>.


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
<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>
</dt>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndismsendnetbufferlistscomplete">
   NdisMSendNetBufferListsComplete</a>
</dt>
<dt>
<a href="netvista.net_buffer">NET_BUFFER</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569102">OID_DOT11_ACTIVE_PHY_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569402">OID_DOT11_POWER_MGMT_REQUEST</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_EXTSTA_SEND_CONTEXT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

