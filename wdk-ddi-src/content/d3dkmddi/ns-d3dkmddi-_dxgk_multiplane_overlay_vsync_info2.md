---
UID: NS.D3DKMDDI._DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
title: _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
author: windows-driver-content
description: Used by new drivers to report per-plane flip completion after a VSYNC.
old-location: display\dxgk_multiplane_overlay_vsync_info2.htm
old-project: display
ms.assetid: CC1371C5-1BAB-458C-BC7F-9844B2BBEA3A
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2, DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2
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

# _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 structure



## -description
Used by new drivers to report per-plane flip completion after a VSYNC.



## -syntax

````
typedef struct _DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2 {
  DWORD                         LayerIndex;
  ULONGLONG                     PresentId;
  DXGKCB_NOTIFY_MPO_VSYNC_FLAGS Flags;
} DXGK_MULTIPLANE_OVERLAY_VSYNC_INFO2;
````


## -struct-fields

### -field LayerIndex

The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.  


### -field PresentId

The 64 bit PresentId specified in the SetVidPnSourceAddressWithMultiPlaneOverlay3() DDI call.


### -field Flags

Flag to indicate whether the scheduler should call DXGKDDI_POSTMULTIPLANEOVERLAYPRESENT for this plane


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h</dt>
</dl>
</td>
</tr>
</table>