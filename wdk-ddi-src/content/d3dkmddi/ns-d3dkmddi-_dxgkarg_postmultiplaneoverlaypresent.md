---
UID: NS:d3dkmddi._DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
title: "_DXGKARG_POSTMULTIPLANEOVERLAYPRESENT"
author: windows-driver-content
description: Contains arguments for the DxgkDdiPostMultiPlaneOverlayPresent function.
old-location: display\dxgkarg_postmultiplaneoverlaypresent.htm
old-project: display
ms.assetid: E257606A-66EE-4F53-B661-F5FFC63E1F54
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dkmddi/DXGKARG_POSTMULTIPLANEOVERLAYPRESENT, DXGKARG_POSTMULTIPLANEOVERLAYPRESENT structure [Display Devices], display.dxgkarg_postmultiplaneoverlaypresent, _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT, DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmddi.h
apiname:
-	DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
product: Windows
targetos: Windows
req.typenames: DXGKARG_POSTMULTIPLANEOVERLAYPRESENT
---

# _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT structure
Contains arguments for the DxgkDdiPostMultiPlaneOverlayPresent function.

## Syntax
````
typedef struct _DXGKARG_POSTMULTIPLANEOVERLAYPRESENT {
  D3DDDI_VIDEO_PRESENT_TARGET_ID VidPnTargetId;
  UINT                           PhysicalAdapterMask;
  DWORD                          LayerIndex;
  ULONGLONG                      PresentId;
} DXGKARG_POSTMULTIPLANEOVERLAYPRESENT;
````

## Members


`LayerIndex`

[in] The zero-based index of the overlay plane to display. The top plane (in the z-direction) has index zero. The planes' index values must be sequential from top to bottom.

`PhysicalAdapterMask`

[in] The physical adapter mask where the vertical sync occurs. If this member contains a valid value, the driver must also set the ValidPhysicalAdapterMask bit-field flag in the Flags member.

`PresentID`



`VidPnTargetId`

[in] The zero-based identification number of the video present target in a path of a video present network (VidPN) topology. This number represents the video present target where the vertical sync occurs.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dkmddi.h |