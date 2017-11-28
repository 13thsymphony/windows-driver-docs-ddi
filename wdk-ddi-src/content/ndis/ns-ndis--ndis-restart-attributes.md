---
UID: NS.ndis._NDIS_RESTART_ATTRIBUTES
title: NDIS_RESTART_ATTRIBUTES
author: windows-driver-content
description: The NDIS_RESTART_ATTRIBUTES structure identifies an attributes entry in a linked list of restart attributes.
old-location: netvista\ndis_restart_attributes.htm
old-project: netvista
ms.assetid: 1f9f4b91-bd1f-4daa-ac98-6372bf55c2ab
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: NDIS_RESTART_ATTRIBUTES,
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
req.alt-api: NDIS_RESTART_ATTRIBUTES
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
req.iface: 
---

# NDIS_RESTART_ATTRIBUTES structure



## -description
<p>The NDIS_RESTART_ATTRIBUTES structure identifies an attributes entry in a linked list of restart
  attributes.</p>


## -syntax

````
typedef struct _NDIS_RESTART_ATTRIBUTES {
  PNDIS_RESTART_ATTRIBUTES Next;
  NDIS_OID                 Oid;
  ULONG                    DataLength;
  UCHAR                    Data[1];
} NDIS_RESTART_ATTRIBUTES, *PNDIS_RESTART_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field <b>Next</b>

<dd>
<p>A pointer to an NDIS_RESTART_ATTRIBUTES structure that you can use to access the next set of
     restart attributes in the linked list of attributes. If there are no additional attributes, this member
     is <b>NULL</b>.</p>
</dd>

### -field <b>Oid</b>

<dd>
<p>The NDIS object identifier for the information that is in the 
     <b>Data</b> member. For example, if 
     <b>Oid</b> is 
     <a href="netvista.oid_gen_miniport_restart_attributes">
     OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>, the 
     <b>Data</b> member contains an 
     <a href="..\ndis\ns-ndis--ndis-restart-general-attributes.md">
     NDIS_RESTART_GENERAL_ATTRIBUTES</a> structure.</p>
</dd>

### -field <b>DataLength</b>

<dd>
<p>The length, in bytes, of the information that is stored in the 
     <b>Data</b> member.</p>
</dd>

### -field <b>Data</b>

<dd>
<p>A buffer that contains the information that is associated with the OID that is specified in the 
     <b>Oid</b> member.</p>
</dd>
</dl>

## -remarks
<p>When NDIS restarts a driver stack, NDIS passes a pointer to a linked list of restart attributes to
    miniport, filter, and protocol drivers.</p>

<p>When it calls a miniport driver's 
    <a href="..\ndis\nc-ndis-miniport-restart.md">MiniportRestart</a> function, NDIS passes a
    pointer to an NDIS_RESTART_ATTRIBUTES structure to the miniport driver in the 
    <b>RestartAttributes</b> member of the 
    <a href="..\ndis\ns-ndis--ndis-miniport-restart-parameters.md">
    NDIS_MINIPORT_RESTART_PARAMETERS</a> structure.</p>

<p>When it calls a filter driver's 
    <a href="..\ndis\nc-ndis-filter-restart.md">FilterRestart</a> function, NDIS passes a
    pointer to an NDIS_RESTART_ATTRIBUTES structure to the filter driver in the 
    <b>RestartAttributes</b> member of the 
    <a href="..\ndis\ns-ndis--ndis-filter-restart-parameters.md">
    NDIS_FILTER_RESTART_PARAMETERS</a> structure.</p>

<p>When it restarts a protocol binding, NDIS provides a pointer to an NDIS_RESTART_ATTRIBUTES structure
    in the 
    <b>RestartAttributes</b> member of the 
    <a href="..\ndis\ns-ndis--ndis-protocol-restart-parameters.md">
    NDIS_PROTOCOL_RESTART_PARAMETERS</a> structure. To restart a protocol binding, NDIS calls a protocol
    driver's 
    <a href="..\ndis\nc-ndis-protocol-net-pnp-event.md">ProtocolNetPnPEvent</a> function. The 
    <b>NetPnPEvent</b> member of the 
    <a href="..\ndis\ns-ndis--net-pnp-event-notification.md">
    NET_PNP_EVENT_NOTIFICATION</a> structure, that NDIS passes to 
    <i>ProtocolNetPnPEvent</i>, contains a 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568751">NET_PNP_EVENT</a> structure. The NET_PNP_EVENT
    structure specifies 
    <b>NetEventRestart</b> in the 
    <b>NetEvent</b> member and a pointer to the NDIS_PROTOCOL_RESTART_PARAMETERS structure in the 
    <b>Buffer</b> member.</p>

<p>If the restart attributes pointer that NDIS passes to NDIS drivers is <b>NULL</b>, the drivers should not
    propagate their attributes changes up the driver stack. In this situation, drivers should not modify, or
    report any attributes changes.</p>

<p>If the restart attributes pointer is not <b>NULL</b>, the linked list of NDIS_RESTART_ATTRIBUTES structures
    has at least one entry that contains an 
    <a href="..\ndis\ns-ndis--ndis-restart-general-attributes.md">
    NDIS_RESTART_GENERAL_ATTRIBUTES</a> structure. The rest of the entries, if any, contain media-specific
    attributes.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\ndis\nc-ndis-filter-restart.md">FilterRestart</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport-restart.md">MiniportRestart</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-filter-restart-parameters.md">
   NDIS_FILTER_RESTART_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-miniport-restart-parameters.md">
   NDIS_MINIPORT_RESTART_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-protocol-restart-parameters.md">
   NDIS_PROTOCOL_RESTART_PARAMETERS</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis--ndis-restart-general-attributes.md">
   NDIS_RESTART_GENERAL_ATTRIBUTES</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568752">NET_PNP_EVENT_NOTIFICATION</a>
</dt>
<dt>
<a href="netvista.oid_gen_miniport_restart_attributes">
   OID_GEN_MINIPORT_RESTART_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-protocol-net-pnp-event.md">ProtocolNetPnPEvent</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_RESTART_ATTRIBUTES structure%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
