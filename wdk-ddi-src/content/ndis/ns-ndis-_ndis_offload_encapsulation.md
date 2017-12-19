---
UID: NS.NDIS._NDIS_OFFLOAD_ENCAPSULATION
title: _NDIS_OFFLOAD_ENCAPSULATION
author: windows-driver-content
description: The NDIS_OFFLOAD_ENCAPSULATION structure specifies encapsulation settings when it is used with the OID_OFFLOAD_ENCAPSULATION OID.
old-location: netvista\ndis_offload_encapsulation.htm
old-project: NetVista
ms.assetid: 19013ffa-6bb5-4a77-b85b-c32fb0bf0530
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_OFFLOAD_ENCAPSULATION, *PNDIS_OFFLOAD_ENCAPSULATION, NDIS_OFFLOAD_ENCAPSULATION, PNDIS_OFFLOAD_ENCAPSULATION
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
req.alt-api: NDIS_OFFLOAD_ENCAPSULATION
req.alt-loc: ndis.h
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

# _NDIS_OFFLOAD_ENCAPSULATION structure



## -description
The NDIS_OFFLOAD_ENCAPSULATION structure specifies encapsulation settings when it is used with the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff569762">OID_OFFLOAD_ENCAPSULATION</a> OID.



## -syntax

````
typedef struct _NDIS_OFFLOAD_ENCAPSULATION {
  NDIS_OBJECT_HEADER Header;
  struct {
    ULONG Enabled;
    ULONG EncapsulationType;
    ULONG HeaderSize;
  } IPv4;
  struct {
    ULONG Enabled;
    ULONG EncapsulationType;
    ULONG HeaderSize;
  } IPv6;
} NDIS_OFFLOAD_ENCAPSULATION, *PNDIS_OFFLOAD_ENCAPSULATION;
````


## -struct-fields

### -field Header

The 
     <a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a> structure for the
     NDIS_OFFLOAD_ENCAPSULATION structure. Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_OFFLOAD_ENCAPSULATION, the 
     <b>Revision</b> member to NDIS_OFFLOAD_ENCAPSULATION_ REVISION _1, and the 
     <b>Size</b> member to NDIS_SIZEOF_OFFLOAD_ENCAPSULATION_REVISION_1.


### -field IPv4

A structure within NDIS_OFFLOAD_ENCAPSULATION that specifies IPv4 encapsulation and that contains
     the following members:
     


### -field Enabled

A ULONG value that enables IPv4 encapsulation. A protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_ON if it is enabling IPv4 large send offload version 1 (LSOV1),
       large send offload version 2 (LSOV2), or checksum offloads. Otherwise, the protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_NO_CHANGE.


### -field EncapsulationType

The IPv4 encapsulation type. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, this member is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>EncapsulationType</b> to one of the following:
       

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field NDIS_ENCAPSULATION_IEEE_802_3

</td>
<td width="60%">
Specifies IEEE 802.3 encapsulation. When this value is specified, a miniport driver should also use NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q or NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB encapsulation where applicable. See documentation for <a href="netvista.ndis_offload">NDIS_OFFLOAD</a> for more information.


</td>
</tr>
<tr>

### -field NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED

</td>
<td width="60%">
Specifies logical link control (LLC) encapsulation for routed protocols, as described in RFC
         1483. This flag is also used to indicate Ethernet LLC/SNAP encapsulation.

</td>
</tr>
</table>
 


### -field HeaderSize

The Ethernet header length that is used in IPv4 packets. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, this member is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>HeaderSize</b> to the size of the Ethernet header that it uses.

</dd>
</dl>

### -field IPv6

A structure within NDIS_OFFLOAD_ENCAPSULATION that specifies IPv6 encapsulation and that contains
     the following members:
     


### -field Enabled

A ULONG value that enables IPv6 encapsulation. A protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_ON if it is enabling IPv6 LSOV1, LSOV2, or checksum offloads.
       Otherwise, the protocol driver sets 
       <b>Enabled</b> to NDIS_OFFLOAD_SET_NO_CHANGE.


### -field EncapsulationType

The IPv6 encapsulation type. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, 
       <b>EncapsulationType</b> is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>EncapsulationType</b> to one of the following:
       

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field NDIS_ENCAPSULATION_IEEE_802_3

</td>
<td width="60%">
Specifies IEEE 802.3 encapsulation. When this value is specified, a miniport driver should also use NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q or NDIS_ENCAPSULATION_IEEE_802_3_P_AND_Q_IN_OOB encapsulation where applicable. See documentation for <a href="netvista.ndis_offload">NDIS_OFFLOAD</a> for more information.


</td>
</tr>
<tr>

### -field NDIS_ENCAPSULATION_IEEE_LLC_SNAP_ROUTED

</td>
<td width="60%">
Specifies LLC encapsulation for routed protocols, as described in RFC 1483. This flag is also
         used to indicate Ethernet LLC/SNAP encapsulation.

</td>
</tr>
</table>
 


### -field HeaderSize

The Ethernet header length that is used in IPv6 packets. If the 
       <b>Enabled</b> member is not set to NDIS_OFFLOAD_SET_ON, this member is zero. If the 
       <b>Enabled</b> member is set to NDIS_OFFLOAD_SET_ON, a protocol driver must set 
       <b>HeaderSize</b> to the size of the Ethernet header that it uses.

</dd>
</dl>

## -remarks
The NDIS_OFFLOAD_ENCAPSULATION structure specifies the requested encapsulation settings that a
    miniport adapter should use for task offload services.

In a set of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff569762">OID_OFFLOAD_ENCAPSULATION</a>, a
    protocol driver specifies an NDIS_OFFLOAD_ENCAPSULATION structure in the 
    <b>InformationBuffer</b> member of the 
    <a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a> structure.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_object_header">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.ndis_oid_request">NDIS_OID_REQUEST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff569762">OID_OFFLOAD_ENCAPSULATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_OFFLOAD_ENCAPSULATION structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

