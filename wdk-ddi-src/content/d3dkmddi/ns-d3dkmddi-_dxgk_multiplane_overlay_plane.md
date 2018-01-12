---
UID: NS:d3dkmddi._DXGK_MULTIPLANE_OVERLAY_PLANE
title: _DXGK_MULTIPLANE_OVERLAY_PLANE
author: windows-driver-content
description: Specifies an overlay plane to display in a call to the DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay function.
old-location: display\dxgk_multiplane_overlay_plane.htm
old-project: display
ms.assetid: 8ea1abc7-b861-4217-a3ab-cf60026d9608
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXGK_MULTIPLANE_OVERLAY_PLANE, DXGK_MULTIPLANE_OVERLAY_PLANE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MULTIPLANE_OVERLAY_PLANE
req.alt-loc: D3dkmddi.h
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
req.typenames: DXGK_MULTIPLANE_OVERLAY_PLANE
---

# _DXGK_MULTIPLANE_OVERLAY_PLANE structure



## -description
Specifies an overlay plane to display in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a> function.



## -syntax

````
typedef struct _DXGK_MULTIPLANE_OVERLAY_PLANE {
  UINT                               LayerIndex;
  BOOL                               Enabled;
  UINT                               AllocationSegment;
  PHYSICAL_ADDRESS                   AllocationAddress;
  HANDLE                             hAllocation;
  DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES PlaneAttributes;
} DXGK_MULTIPLANE_OVERLAY_PLANE;
````


## -struct-fields

### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.


### -field Enabled

Indicates whether the overlay plane specified by <b>LayerIndex</b> is enabled for display.

If <b>FALSE</b>, the display miniport driver should disable the specified overlay plane.

If a plane was enabled during a previous call to <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>, the driver should continue to display the plane without flipping it.


### -field AllocationSegment

[in] The identifier of a segment that data is read from.


### -field AllocationAddress

[in] A <b>PHYSICAL_ADDRESS</b> data type (which is defined as <b>LARGE_INTEGER</b>) that indicates the physical address, within the segment that <b>AllocationSegment</b> specifies, where the data is read.


### -field hAllocation

A handle to the allocation to be displayed on the overlay plane.


### -field PlaneAttributes

A structure of type <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>  that specifies overlay plane attributes.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

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
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_allocationinfo.md">DXGK_ALLOCATIONINFO</a>
</dt>
<dt>
<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_multiplane_overlay_attributes.md">DXGK_MULTIPLANE_OVERLAY_ATTRIBUTES</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createallocation.md">DxgkDdiCreateAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_setvidpnsourceaddresswithmultiplaneoverlay.md">DxgkDdiSetVidPnSourceAddressWithMultiPlaneOverlay</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGK_MULTIPLANE_OVERLAY_PLANE structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

