---
UID: NS.ucxroothub._ROOTHUB_20PORTS_INFO
title: ROOTHUB_20PORTS_INFO
author: windows-driver-content
description: This structure that has an array of 2.0 ports supported by the root hub. This structure is provided by UCX in a framework request in the EVT_UCX_ROOTHUB_GET_20PORT_INFO callback function.
old-location: buses\_roothub_20ports_info.htm
old-project: usbref
ms.assetid: FBFDF368-8DB9-4ACE-851D-6A178FB3E019
ms.author: windowsdriverdev
ms.date: 11/20/2017
ms.keywords: ROOTHUB_20PORTS_INFO, ROOTHUB_20PORTS_INFO, *PROOTHUB_20PORTS_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxroothub.h
req.include-header: Ucxclass.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ROOTHUB_20PORTS_INFO
req.alt-loc: ucxroothub.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# ROOTHUB_20PORTS_INFO structure



## -description
<p>This structure that has an array of 2.0 ports supported by the  root hub. This structure is provided by  UCX in a framework request in the  <a href="buses.evt_ucx_roothub_get_20port_info">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a> callback function.</p>


## -syntax

````
typedef struct _ROOTHUB_20PORTS_INFO {
  ULONG                Size;
  USHORT               NumberOfPorts;
  USHORT               PortInfoSize;
  PROOTHUB_20PORT_INFO *PortInfoArray;
} ROOTHUB_20PORTS_INFO, *P_ROOTHUB_20PORTS_INFO;
````


## -struct-fields
<dl>

### -field <b>Size</b>

<dd>
<p>The size in bytes of this structure.</p>
</dd>

### -field <b>NumberOfPorts</b>

<dd>
<p>The number of USB 2.0 ports connected to the root hub. </p>
</dd>

### -field <b>PortInfoSize</b>

<dd>
<p>The size of the <b>ROOTHUB_20PORTS_INFO</b> structure.</p>
</dd>

### -field <b>PortInfoArray</b>

<dd>
<p>A pointer to an array of <a href="buses._roothub_20port_info">PROOTHUB_20PORT_INFO</a> structures.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ucxroothub.h (include Ucxclass.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="buses.evt_ucx_roothub_get_20port_info">EVT_UCX_ROOTHUB_GET_20PORT_INFO</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20ROOTHUB_20PORTS_INFO structure%20 RELEASE:%20(11/20/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
