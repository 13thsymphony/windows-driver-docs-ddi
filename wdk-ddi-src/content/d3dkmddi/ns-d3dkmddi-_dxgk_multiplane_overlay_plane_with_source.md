---
UID: NS.D3DKMDDI._DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
title: _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
author: windows-driver-content
description: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE describes the multi-plane overlay plane attributes, allocation, and video present network source identification number.
old-location: display\dxgk_multiplane_overlay_plane_with_source.htm
old-project: display
ms.assetid: 358C060B-23A0-4F02-A5D3-07ADC3435849
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE, DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE
req.alt-loc: d3dkmddi.h
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
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE structure



## -description
<b>DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE</b>

describes the multi-plane overlay plane attributes, allocation, and video present network source identification number.



## -syntax

````
typedef struct _DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE {
  HANDLE                              hAllocation;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID      VidPnSourceId;
  UINT                                LayerIndex;
  DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2 PlaneAttributes;
} DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE;
````


## -struct-fields

### -field hAllocation

A handle to the allocation.

### -field VidPnSourceId

The zero-based video present network source identification number of the input for which the support levels are queried.

### -field LayerIndex

The index of the layer being queried.

### -field PlaneAttributes

A <a href="display.dxgk_multiplane_overlay_attributes2">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a> structure that specifies overlay plane attributes.

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.dxgk_multiplane_overlay_attributes2">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES2</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MULTIPLANE_OVERLAY_PLANE_WITH_SOURCE structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
