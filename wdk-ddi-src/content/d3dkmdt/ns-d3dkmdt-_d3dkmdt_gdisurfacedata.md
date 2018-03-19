---
UID: NS:d3dkmdt._D3DKMDT_GDISURFACEDATA
title: "_D3DKMDT_GDISURFACEDATA"
author: windows-driver-content
description: The D3DKMDT_GDISURFACEDATA structure describes surfaces that are used by GDI hardware acceleration and the Desktop Window Manager (DWM).
old-location: display\d3dkmdt_gdisurfacedata.htm
old-project: display
ms.assetid: 7ae789dd-2454-4ed6-bd26-5ebfd9c33768
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_GDISURFACEDATA, D3DKMDT_GDISURFACEDATA structure [Display Devices], DmStructs_91525c19-9d84-4406-b456-c6d80cb0f1d3.xml, _D3DKMDT_GDISURFACEDATA, d3dkmdt/D3DKMDT_GDISURFACEDATA, display.d3dkmdt_gdisurfacedata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 7.
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmdt.h
api_name:
-	D3DKMDT_GDISURFACEDATA
product: Windows
targetos: Windows
req.typenames: D3DKMDT_GDISURFACEDATA
---

# _D3DKMDT_GDISURFACEDATA structure
The D3DKMDT_GDISURFACEDATA structure describes surfaces that are used by GDI hardware acceleration and the Desktop Window Manager (DWM).

## Syntax
````
typedef struct _D3DKMDT_GDISURFACEDATA {
  UINT                    Width;
  UINT                    Height;
  D3DDDIFORMAT            Format;
  D3DKMDT_GDISURFACETYPE  Type;
  D3DKMDT_GDISURFACEFLAGS Flags;
  UINT                    Pitch;
} D3DKMDT_GDISURFACEDATA;
````

## Members


`Width`

[in] The width of the surface, in pixels.

`Height`

[in] The height of the surface, in pixels.

`Format`

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the surface. The following formats are supported:

D3DDDIFMT_A8B8G8R8

D3DDDIFMT_X8B8G8R8

D3DDDIFMT_A8R8G8B8

D3DDDIFMT_X8R8G8B8

D3DDDIFMT_A8

The D3DDDIFMT_A8 format is used only for D3DKMDT_GDISURFACE_STAGING and D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE staging surface types from the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a> enumeration.

`Type`

[in] A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>-typed value that indicates the surface type.

`Flags`

[in] Reserved for future use. Must be zero.

`Pitch`

[out] The width of the surface, which includes padding, in bytes. The display miniport driver must return the pitch value for all allocations of <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a> type D3DKMDT_GDISURFACE_STAGING_CPUVISIBLE,  D3DKMDT_GDISURFACE_EXISTINGSYSMEM, and D3DKMDT_GDISURFACE_TEXTURE_CROSSADAPTER.

## Remarks
The D3DKMDT_GDISURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a> function. This call generates a description of a surface that can be used for redirection by GDI hardware acceleration and the DWM.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 7. Supported starting with Windows 7. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_present.md">DxgkDdiPresent</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_getstandardallocationdriverdata.md">DxgkDdiGetStandardAllocationDriverData</a>



<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_gdisurfacetype.md">D3DKMDT_GDISURFACETYPE</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>