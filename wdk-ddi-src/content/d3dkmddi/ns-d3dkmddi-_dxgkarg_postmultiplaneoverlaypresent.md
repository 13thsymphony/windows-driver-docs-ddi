---
UID: NS.D3DKMDDI._DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
title: _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
author: windows-driver-content
description: Contains arguments for the DxgkDdiPostMultiPlaneOverlayPresent function.
old-location: display\dxgkarg_postmultiplaneoverlaypresent.htm
old-project: display
ms.assetid: E257606A-66EE-4F53-B661-F5FFC63E1F54
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT, DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
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
req.alt-api: DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
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

# _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT structure



## -description
Contains arguments for the DxgkDdiPostMultiPlaneOverlayPresent function.



## -syntax

````
typedef struct _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT {
  D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId;
  UINT                           PhysicalAdapterMask;
  DWORD                          LayerIndex;
  ULONGLONG                      PresentId;
} DXGKARG_POSTMULTIPLANEOVERLAYPRESENT;
````


## -struct-fields

### -field VidPnTargetId

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.


### -field PhysicalAdapterMask

[in] The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the ValidPhysicalAdapterMask bit-field flag in the Flags member.


### -field LayerIndex

[in] The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom. 


### -field PresentId

      [in] 64 bit integer value representing each flip request for a particular MPO plane.


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