---
UID: NS.d3d12umddi.D3D12DDI_RESOURCE_RANGED_BARRIER_0022
title: D3D12DDI_RESOURCE_RANGED_BARRIER_0022
author: windows-driver-content
description: Describes a resource ranged barrier.
old-location: display\d3d12ddi_resource_ranged_barrier_0022.htm
ms.assetid: 759BA42A-2F38-42D3-A245-8DEA2919DC39
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_RESOURCE_RANGED_BARRIER_0022
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
ms.keywords: D3D12DDI_RESOURCE_RANGED_BARRIER_0022, D3D12DDI_RESOURCE_RANGED_BARRIER_0022
req.iface: 
---

# D3D12DDI_RESOURCE_RANGED_BARRIER_0022 structure



## -description
<p>Describes a resource ranged barrier.</p>


## -syntax

````
typedef struct D3D12DDI_RESOURCE_RANGED_BARRIER_0022 {
  D3D12DDI_HRESOURCE hResource;
  UINT               Subresource;
  D3D12DDI_RANGE     Range;
} D3D12DDI_RESOURCE_RANGED_BARRIER_0022;
````


## -struct-fields
<dl>

### -field <b>hResource</b>

<dd>
<p>The handle of a resource. A null value means that the entire GPU cache must be flushed or invalidated. A non-null value means that the flush or invalidate action affects a smaller subset of the cache that can contain data for that resource. </p>
</dd>

### -field <b>Subresource</b>

<dd>
<p>A subresource. If the <i>Subresource</i> value  is -1 or _ALL_SUBRESOURCES, then a flush or invalidate action need only affect the part of the cache where the entire <i>hResource</i> may reside. If <i>Subresource</i> is not  _ALL_SUBRESOURCES,  a valid subresource index is specified and the <i>Range</i> may further constrain the impact of the operation. </p>
</dd>

### -field <b>Range</b>

<dd>
<p>A range as a <a href="https://msdn.microsoft.com/B3A8F252-D56D-4F20-A0DE-2A29904BC907">D3D12DDI_RANGE</a> structure. If the resource is a texture with an adapter-dependent layout, the range must be (0, UINT64_MAX), because only the driver knows where a particular subresource resides. When the resource is a buffer or texture with well-specified layout, the range fits within the subresource extent. Empty ranges are never passed.</p>
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

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/B3A8F252-D56D-4F20-A0DE-2A29904BC907">D3D12DDI_RANGE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D12DDI_RESOURCE_RANGED_BARRIER_0022 structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
