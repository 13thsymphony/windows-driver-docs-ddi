---
UID: NS.ntddndis._NDIS_WMI_EVENT_HEADER
title: NDIS_WMI_EVENT_HEADER
author: windows-driver-content
description: The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.
old-location: netvista\ndis_wmi_event_header.htm
old-project: netvista
ms.assetid: b9e2c393-cf77-4193-ba59-b8eb914ef1e6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: NDIS_WMI_EVENT_HEADER, NDIS_WMI_EVENT_HEADER, *PNDIS_WMI_EVENT_HEADER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NDIS_WMI_EVENT_HEADER
req.alt-loc: ntddndis.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.iface: 
---

# NDIS_WMI_EVENT_HEADER structure



## -description
<p>The NDIS_WMI_EVENT_HEADER structure provides information about a GUID event for WMI clients.</p>


## -syntax

````
typedef struct _NDIS_WMI_EVENT_HEADER {
  NDIS_OBJECT_HEADER Header;
  NET_IFINDEX        IfIndex;
  NET_LUID           NetLuid;
  ULONG64            RequestId;
  NDIS_PORT_NUMBER   PortNumber;
  ULONG              DeviceNameLength;
  ULONG              DeviceNameOffset;
  UCHAR              Padding[4];
} NDIS_WMI_EVENT_HEADER, *PNDIS_WMI_EVENT_HEADER;
````


## -struct-fields
<dl>

### -field Header

<dd>
<p>The 
     <a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a> structure for this
     NDIS_WMI_EVENT_HEADER structure. Set the 
     <b>Type</b> member of NDIS_OBJECT_HEADER to NDIS_WMI_OBJECT_TYPE_EVENT, the 
     <b>Revision</b> member to NDIS_WMI_EVENT_HEADER_REVISION_1, and the 
     <b>Size</b> member to 
     sizeof(NDIS_WMI_EVENT_HEADER).</p>
</dd>

### -field IfIndex

<dd>
<p>The NDIS interface index of the NDIS miniport adapter interface that is associated with the
     GUID.</p>
</dd>

### -field NetLuid

<dd>
<p>The NDIS network interface name of the miniport adapter.</p>
</dd>

### -field RequestId

<dd>
<p>An identifier for the request. If a miniport driver must complete a request immediately and it
     completes the request with a status of NDIS_STATUS_INDICATION_REQUIRED, the miniport driver uses this 
     <b>RequestId</b> value to set the 
     <b>RequestId</b> member of the associated 
     <a href="..\ndis\ns-ndis--ndis-status-indication.md">NDIS_STATUS_INDICATION</a> structure. 
     </p>
<p>NDIS or overlying drivers can also use the 
     <b>RequestId</b> to cancel a request. When a miniport driver receives a
     cancellation request, the miniport driver cancels any pending requests with a matching 
     <b>RequestId</b>. If 
     <b>RequestId</b> is zero, the miniport driver can ignore this member.</p>
<p>For more information about this member, see 
     <a href="..\ndis\ns-ndis--ndis-oid-request.md">NDIS_OID_REQUEST</a>.</p>
</dd>

### -field PortNumber

<dd>
<p>The miniport adapter port, if any. If the GUID is not specific to a port, 
     <b>PortNumber</b> is zero.</p>
</dd>

### -field DeviceNameLength

<dd>
<p>The length, in bytes, of the device name.</p>
</dd>

### -field DeviceNameOffset

<dd>
<p>The offset, in bytes, to the beginning of the device name from the beginning of the
     NDIS_WMI_EVENT_HEADER structure.</p>
</dd>

### -field Padding

<dd>
<p>This member is reserved.</p>
</dd>
</dl>

## -remarks
<p>NDIS translates NDIS status indications to WMI GUID event indications.</p>

<p>WMI GUID event indications that are specific to NDIS 6.0 and later versions include an
    NDIS_WMI_EVENT_HEADER structure that is followed by the GUID-specific data, if any.</p>

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
<dt>Ntddndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\ntddndis\ns-ntddndis--ndis-object-header.md">NDIS_OBJECT_HEADER</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WMI_EVENT_HEADER structure%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
