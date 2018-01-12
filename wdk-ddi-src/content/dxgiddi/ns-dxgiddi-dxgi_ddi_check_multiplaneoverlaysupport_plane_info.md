---
UID: NS:dxgiddi.DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO
title: DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO
author: windows-driver-content
description: Specifies the support attributes that the hardware provides for multiplane overlays.
old-location: display\dxgi_ddi_check_multiplaneoverlaysupport_plane_info.htm
old-project: display
ms.assetid: 3a1e41b5-cd62-436b-a4ed-6dee99c03cac
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO, DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
req.alt-loc: Dxgiddi.h
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
req.typenames: DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
---

# DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO structure



## -description
Specifies the support attributes that the hardware provides for multiplane overlays.



## -syntax

````
typedef struct DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO {
  DXGI_DDI_HRESOURCE                     hResource;
  UINT                                   SubResourceIndex;
  DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES PlaneAttributes;
} DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO;
````


## -struct-fields

### -field hResource

A handle to the resource. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the resource.


### -field SubResourceIndex

The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or surface, on which an overlay plane is to be displayed.


### -field PlaneAttributes

A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_multiplane_overlay_attributes.md">DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.


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
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>