---
UID: NS:dxgiddi.DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO
title: DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO
author: windows-driver-content
description: Specifies the support attributes that the hardware provides for multiplane overlays.
old-location: display\dxgi_ddi_check_multiplaneoverlaysupport_plane_info.htm
old-project: display
ms.assetid: 3a1e41b5-cd62-436b-a4ed-6dee99c03cac
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO, DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO structure [Display Devices], DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO, DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO structure [Display Devices], display.dxgi_ddi_check_multiplaneoverlaysupport_plane_info, dxgiddi/DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dxgiddi.h
api_name:
-	DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
product: Windows
targetos: Windows
req.typenames: DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO
---

# DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO structure
Specifies the support attributes that the hardware provides for multiplane overlays.

## Syntax
````
typedef struct DXGI_DDI_CHECK_MULTIPLANEOVERLAYSUPPORT_PLANE_INFO {
  DXGI_DDI_HRESOURCE                     hResource;
  UINT                                   SubResourceIndex;
  DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES PlaneAttributes;
} DXGI_DDI_CHECK_MULTIPLANE_OVERLAY_SUPPORT_PLANE_INFO;
````

## Members


`hResource`

A handle to the resource. The display miniport driver must set this member to a value that it can use to refer to its private tracking structure for the resource.

`PlaneAttributes`

A <a href="..\dxgiddi\ns-dxgiddi-dxgi_ddi_multiplane_overlay_attributes.md">DXGI_DDI_MULTIPLANE_OVERLAY_ATTRIBUTES</a> structure that specifies overlay plane attributes.

`SubResourceIndex`

The zero-based index into the resource, which is specified by the handle in the <b>hResource</b> member. This index indicates the subresource, or surface, on which an overlay plane is to be displayed.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1 Windows 8.1 |
| **Header** | dxgiddi.h (include D3d10umddi.h) |