---
UID: NS.ks.PKSP_NODE
title: PKSP_NODE
author: windows-driver-content
description: Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request.
old-location: stream\ksp_node.htm
old-project: stream
ms.assetid: 2d5f1b31-d8fe-40a3-ac23-cc442f3adbe5
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: PKSP_NODE, KSP_NODE, *PKSP_NODE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ks.h
req.include-header: Ks.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KSP_NODE
req.alt-loc: ks.h
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
req.iface: 
---

# PKSP_NODE structure



## -description
<p>Kernel streaming clients use the KSP_NODE structure to specify the property and node type within a KSPROPERTY_TOPOLOGY_NAME property request.</p>


## -syntax

````
typedef struct {
  KSPROPERTY Property;
  ULONG      NodeId;
  ULONG      Reserved;
} KSP_NODE, *PKSP_NODE;
````


## -struct-fields
<dl>

### -field <b>Property</b>

<dd>
<p>Specifies a <a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a> structure.</p>
</dd>

### -field <b>NodeId</b>

<dd>
<p>Specifies the node ID.</p>
</dd>

### -field <b>Reserved</b>

<dd>
<p>Reserved for system use. Should be set to zero.</p>
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
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="audio.ksnodeproperty">KSNODEPROPERTY</a>
</dt>
<dt>
<a href="..\ks\nf-ks-ikscontrol-ksproperty.md">KSPROPERTY</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KSP_NODE structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
