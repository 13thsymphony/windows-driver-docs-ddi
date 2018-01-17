---
UID: NE:fwpsk.FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4_
title: FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4_
author: windows-driver-content
description: The FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4 enumeration type specifies the data field identifiers for the FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V4 and FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V4_DISCARD run-time filtering layers.
old-location: netvista\fwps_fields_ale_auth_recv_accept_v4.htm
old-project: netvista
ms.assetid: 8df0b735-26af-4ae3-a8bb-928f4f6068a2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4_, FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: fwpsk.h
req.include-header: Fwpsk.h
req.target-type: Windows
req.target-min-winverclnt: Unless otherwise noted, supported starting with Windows Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4
req.alt-loc: fwpsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4
---

# FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4_ enumeration



## -description
The FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4 enumeration type specifies the data field identifiers for the
  FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V4 and FWPS_LAYER_ALE_AUTH_RECV_ACCEPT_V4_DISCARD 
  <a href="netvista.run_time_filtering_layer_identifiers">run-time filtering layers</a>.



## -syntax

````
typedef enum FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4_ { 
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_APP_ID,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_USER_ID,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_ADDRESS,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_ADDRESS_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_PORT,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_PROTOCOL,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_REMOTE_ADDRESS,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_REMOTE_PORT,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_REMOTE_USER_ID,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_REMOTE_MACHINE_ID,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_INTERFACE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_FLAGS,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_SIO_FIREWALL_SYSTEM_PORT,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NAP_CONTEXT,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_INTERFACE_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_TUNNEL_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_INTERFACE_INDEX,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_SUB_INTERFACE_INDEX,
#if (NTDDI_VERSION >= NTDDI_WIN6SP1)
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_ARRIVAL_INTERFACE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ARRIVAL_INTERFACE_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ARRIVAL_TUNNEL_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ARRIVAL_INTERFACE_INDEX,
#if (NTDDI_VERSION >= NTDDI_WIN7)
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_SUB_INTERFACE_INDEX,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_NEXTHOP_INTERFACE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_INTERFACE_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_TUNNEL_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_INTERFACE_INDEX,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ORIGINAL_PROFILE_ID,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_CURRENT_PROFILE_ID,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_REAUTHORIZE_REASON,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ORIGINAL_ICMP_TYPE,
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_INTERFACE_QUARANTINE_EPOCH,
#if (NTDDI_VERSION >= NTDDI_WIN8)
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_PACKAGE_ID,
#endif 
#endif 
#endif 
  FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_MAX
} FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4;
````


## -enum-fields

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_APP_ID

The full path of the application.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_USER_ID

The identifier of the local user.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_ADDRESS

The local IP address.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_ADDRESS_TYPE

The local IP address type. The possible values are defined by the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a> enumeration.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_PORT

The local transport protocol port number.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_PROTOCOL

The IP protocol number, as specified in RFC 1700.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_REMOTE_ADDRESS

The remote IP address.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_REMOTE_PORT

The remote transport protocol port number.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_REMOTE_USER_ID

The identifier of the remote user.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_REMOTE_MACHINE_ID

The identifier of the remote machine.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_LOCAL_INTERFACE

The locally unique identifier (<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>) for the network interface associated with the
     local IP address.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_FLAGS

A bitwise OR of a combination of filtering condition flags. For information about the possible
     flags, see 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a>.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_SIO_FIREWALL_SYSTEM_PORT

Reserved for internal use.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NAP_CONTEXT

Reserved for internal use.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_INTERFACE_TYPE

The type of the local network interface, as defined by the Internet Assigned Numbers Authority
     (IANA). For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by the IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_INTERFACE_INDEX

The index of the arrival network interface, as enumerated by the network stack.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_SUB_INTERFACE_INDEX

The LUID for the network interface that is associated with the arrival IP address.


### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_ARRIVAL_INTERFACE

The LUID for the network interface that is associated with the arrival IP address.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ARRIVAL_INTERFACE_TYPE

The type of the arrival network interface, as defined by the Internet Assigned Numbers Authority
     (IANA). For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ARRIVAL_TUNNEL_TYPE

The encapsulation method used by a tunnel if the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by the IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ARRIVAL_INTERFACE_INDEX

The index of the arrival network interface, as enumerated by the network stack.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_SUB_INTERFACE_INDEX

The index of the logical network interface that will be used to continue forwarding of the
     outbound packet, as enumerated by the network stack.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_IP_NEXTHOP_INTERFACE

The LUID for the network interface that is the next interface for the forwarding of the outbound
     packet.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_INTERFACE_TYPE

The type of the network interface that will be used to continue forwarding of the outbound packet,
     as defined by the Internet Assigned Numbers Authority (IANA). For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_TUNNEL_TYPE

The encapsulation method used by a tunnel for the forwarding interface of the outbound packet, if
     the 
     <b>IfType</b> member of the IP_ADAPTER_ADDRESSES structure is IF_TYPE_TUNNEL. The tunnel type is defined
     by the IANA. For more information, see 
     <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a>.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_NEXTHOP_INTERFACE_INDEX

The index of the network interface that will be used to continue forwarding of the outbound
     packet, as enumerated by the network stack.
     

<div class="alert"><b>Note</b>  Supported in Windows Server 2008, Windows Vista SP1, and later versions of
     Windows.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ORIGINAL_PROFILE_ID

The original profile identifier (network category) of the network interface. The possible network
     category values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_CURRENT_PROFILE_ID

The current profile identifier (network category) of the network interface. The possible network
     category values are: public (1), private (2), or domain (3).
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_REAUTHORIZE_REASON

The reason for reauthorizing a previously authorized connection. For more information about
     reasons for reauthorization, see 
     the Filtering Condition Reauthorization Flag of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff549942">Filtering Condition Flags</a> topic.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ORIGINAL_ICMP_TYPE

The original ICMP type for an exchange. The ICMP type field, as specified in RFC 792.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_INTERFACE_QUARANTINE_EPOCH

The time that has passed since the last media state change occurred for the network interface.
     

<div class="alert"><b>Note</b>  Supported starting with Windows 7.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_ALE_PACKAGE_ID

The package identifier is a security identifier (SID) that identifies the associated AppContainer process. For more information about the SID structure, see the description for the SID structure in the Microsoft Windows SDK documentation.

<div class="alert"><b>Note</b>  Supported starting with Windows 8.</div>
<div> </div>

### -field FWPS_FIELD_ALE_AUTH_RECV_ACCEPT_V4_MAX

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks
In Windows Server 2008, Windows Vista SP1, and later versions of Windows, when an outbound packet is
    indicated to this layer during a reauthorization call to the callout filter's 
    <a href="..\fwpsk\nc-fwpsk-fwps_callout_classify_fn0.md">classifyFn</a> function, all arrival network
    interface related fields are set to FWP_EMPTY.

The following macros in 
    <i>Fwpsk.h</i> are defined with FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4 enumeration
    values:

These macros are used to access the following IPV4 data fields:



The ICMP type field, as specified in RFC 792.

The ICMP code field, as specified in RFC 792.

The type of the local network interface, as defined by the Internet Assigned Numbers Authority
       (IANA). For more information, see IANAifType-MIB Definitions.

The encapsulation method used by a tunnel if the IfType member of the IP_ADAPTER_ADDRESSES
       structure is IF_TYPE_TUNNEL. The tunnel type is defined by IANA. For more information, see 
       <a href="http://go.microsoft.com/fwlink/p/?linkid=60066">IANAifType-MIB Definitions</a> and the
       Windows SDK.

The index of the local network interface, as enumerated by the network stack.

The index of the logical network interface, as enumerated by the network stack.

The IP_PROTECTION_LEVEL property associated with the socket.


## -see-also
<dl>
<dt>
<a href="..\igpupvdev\ns-igpupvdev-_luid.md">LUID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568757">NL_ADDRESS_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20FWPS_FIELDS_ALE_AUTH_RECV_ACCEPT_V4 enumeration%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

