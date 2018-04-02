---
UID: NS:d3dkmddi._DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
title: "_DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT"
author: windows-driver-content
description: Used in a call to the DxgkDdiCheckMultiPlaneOverlaySupport function to check details on hardware support for multiplane overlays.
old-location: display\dxgkarg_checkmultiplaneoverlaysupport.htm
old-project: display
ms.assetid: BAFC7DD1-56F8-47CE-8914-54531BBC3165
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*IN_OUT_PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure [Display Devices], PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure pointer [Display Devices], _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, d3dkmddi/DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, d3dkmddi/PDXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT, display.dxgkarg_checkmultiplaneoverlaysupport"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmddi.h
api_name:
-	DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
product:
- Windows
targetos: Windows
req.typenames: DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT
---

# _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT structure
Used in a call to the <a href="https://msdn.microsoft.com/8332DD64-B75E-40A4-9D98-3406187150F2">DxgkDdiCheckMultiPlaneOverlaySupport</a> function to check details on hardware support for multiplane overlays.

## Syntax
```
typedef struct _DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT {
  UINT                                              PlaneCount;
  DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE       *pPlanes;
  BOOL                                              Supported;
  DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_RETURN_INFO ReturnInfo;
} DXGKARG_CHECKMULTIPLANEOVERLAYSUPPORT;
```

## Members


`PlaneCount`

The number of overlay planes that the hardware supports.

`pPlanes`

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn305132">DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE</a> structure that specifies support attributes that the hardware provides for multiplane overlays.

`Supported`

<b>TRUE</b> if the hardware supports multiplane overlays, otherwise <b>FALSE</b>.

`ReturnInfo`

Specifies limitations on hardware support of multiplane overlays.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | d3dkmddi.h (include D3dkmddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn305132">DXGK_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE</a>



<a href="https://msdn.microsoft.com/8332DD64-B75E-40A4-9D98-3406187150F2">DxgkDdiCheckMultiPlaneOverlaySupport</a>