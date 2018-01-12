---
UID: NS:windot11._DOT11_INCOMING_ASSOC_DECISION
title: _DOT11_INCOMING_ASSOC_DECISION
author: windows-driver-content
description: Important  The Native 802.11 Wireless LAN interface is deprecated in Windows 10 and later.
old-location: netvista\dot11_incoming_assoc_decision.htm
old-project: netvista
ms.assetid: aaddff8c-71da-475b-a395-ac40b3b787ae
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: _DOT11_INCOMING_ASSOC_DECISION, DOT11_INCOMING_ASSOC_DECISION, *PDOT11_INCOMING_ASSOC_DECISION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: windot11.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_INCOMING_ASSOC_DECISION
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
req.typenames: DOT11_INCOMING_ASSOC_DECISION, *PDOT11_INCOMING_ASSOC_DECISION
req.product: Windows 10 or later.
---

# _DOT11_INCOMING_ASSOC_DECISION structure



## -description

## -syntax

````
typedef struct _DOT11_INCOMING_ASSOC_DECISION {
  NDIS_OBJECT_HEADER Header;
  DOT11_MAC_ADDRESS  PeerMacAddr;
  BOOLEAN            bAccept;
  USHORT             usReasonCode;
  ULONG              uAssocResponseIEsOffset;
  ULONG              uAssocResponseIEsLength;
} DOT11_INCOMING_ASSOC_DECISION, *PDOT11_INCOMING_ASSOC_DECISION;
````


## -struct-fields

### -field Header

The type, revision, and size of the DOT11_INCOMING_ASSOC_DECISION structure. This member is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure.
     

The miniport driver must set the members of 
     <b>Header</b> to the following values:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>

### -field Type

</td>
<td width="60%">
This member must be set to NDIS_OBJECT_TYPE_DEFAULT.

</td>
</tr>
<tr>

### -field Revision

</td>
<td width="60%">
This member must be set to DOT11_INCOMING_ASSOC_DECISION_REVISION_1.

</td>
</tr>
<tr>

### -field Size

</td>
<td width="60%">
This member must be set to 
       <code>sizeof(DOT11_INCOMING_ASSOC_DECISION)</code>.

</td>
</tr>
</table>
 

For more information about these members, see 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>.


### -field PeerMacAddr

The media access control (MAC) address of the peer station that the 802.11 station attempted to
     connect to.


### -field bAccept

A Boolean value that indicates whether the miniport driver accepts the incoming association
     request. If <b>TRUE</b>, the driver instructs the NIC to accept the association request. Otherwise, the NIC
     should reject the request.


### -field usReasonCode

A USHORT value that represents a reason code to include in the NIC's association response if 
     <b>bAccept</b> is <b>FALSE</b>.


### -field uAssocResponseIEsOffset

The offset of the additional information elements (IEs), in bytes, which the NIC must add to the
     association response frame that it sends to the peer station that seeks association. This offset is relative
     to the start of the buffer that contains the DOT11_INCOMING_ASSOC_DECISION structure. The default value
     is zero.


### -field uAssocResponseIEsLength

The length of the additional information elements (IEs), in bytes, which the NIC must add to the
     probe response frame that it sends to the peer station that seeks association. The default value is
     zero.


## -remarks
This structure is used with 
    <a href="netvista.oid_dot11_incoming_association_decision">
    OID_DOT11_INCOMING_ASSOCIATION_DECISION</a>.


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows 7 and later versions of the Windows operating
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
<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>
</dt>
<dt>
<a href="netvista.oid_dot11_incoming_association_decision">
   OID_DOT11_INCOMING_ASSOCIATION_DECISION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DOT11_INCOMING_ASSOC_DECISION structure%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

