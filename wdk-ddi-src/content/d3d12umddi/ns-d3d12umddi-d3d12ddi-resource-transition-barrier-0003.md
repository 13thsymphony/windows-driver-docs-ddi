---
UID: NS.d3d12umddi.D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
title: D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
author: windows-driver-content
description: Describes a transition barrier between subresources.
old-location: display\d3d12ddi_resource_transition_barrier_0003.htm
old-project: display
ms.assetid: 86E2A0A4-F02C-43E7-8CC1-395B444299A6
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003, D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003
req.alt-loc: D3d12umddi.h
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

# D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 structure



## -description
<p>Describes a transition barrier between subresources.</p>


## -syntax

````
typedef struct D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003 {
  D3D12DDI_HRESOURCE       hResource;
  UINT                     Subresource;
  D3D12DDI_RESOURCE_STATES StateBefore;
  D3D12DDI_RESOURCE_STATES StateAfter;
} D3D12DDI_RESOURCE_TRANSITION_BARRIER_0003;
````


## -struct-fields
<dl>

### -field hResource

<dd>
<p>The handle of a resource.</p>
</dd>

### -field Subresource

<dd>
<p>A subresource.</p>
</dd>

### -field StateBefore

<dd>
<p>The state before a transition.</p>
</dd>

### -field StateAfter

<dd>
<p>The state after a transition.</p>
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
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>