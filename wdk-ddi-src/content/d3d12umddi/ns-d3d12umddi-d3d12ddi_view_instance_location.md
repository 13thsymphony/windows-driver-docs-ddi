---
UID: NS.D3D12UMDDI.D3D12DDI_VIEW_INSTANCE_LOCATION
title: D3D12DDI_VIEW_INSTANCE_LOCATION
author: windows-driver-content
description: View instance location.
old-location: display\d3d12ddi-view-instance-location.htm
old-project: display
ms.assetid: 1b31ac34-233b-4246-a1c3-d0aac0f35db6
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D12DDI_VIEW_INSTANCE_LOCATION, D3D12DDI_VIEW_INSTANCE_LOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIEW_INSTANCE_LOCATION
req.alt-loc: d3d12umddi.h
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
---

# D3D12DDI_VIEW_INSTANCE_LOCATION structure



## -description
View instance location.



## -syntax

````
typedef struct _D3D12DDI_VIEW_INSTANCE_LOCATION {
  UINT  ViewportArrayIndex;
  UINT  RenderTargetArrayIndex;
} D3D12DDI_VIEW_INSTANCE_LOCATION, D3D12DDI_VIEW_INSTANCE_LOCATION;
````


## -struct-fields

### -field ViewportArrayIndex

Viewport array index.


### -field RenderTargetArrayIndex

Render target array index.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>