---
UID: NS:d3dkmdt._D3DKMDT_SHADOWSURFACEDATA
title: "_D3DKMDT_SHADOWSURFACEDATA"
author: windows-driver-content
description: The D3DKMDT_SHADOWSURFACEDATA structure describes a lockable shadow surface, which matches the primary surface in format and resolution for a given display mode.
old-location: display\d3dkmdt_shadowsurfacedata.htm
old-project: display
ms.assetid: 1b7f6a39-b0d3-4a0b-b030-b7fef3ab58d6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DKMDT_SHADOWSURFACEDATA, D3DKMDT_SHADOWSURFACEDATA structure [Display Devices], DmStructs_645dbefc-137b-47c5-aa4b-de9037d71182.xml, _D3DKMDT_SHADOWSURFACEDATA, d3dkmdt/D3DKMDT_SHADOWSURFACEDATA, display.d3dkmdt_shadowsurfacedata
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
-	D3DKMDT_SHADOWSURFACEDATA
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_SHADOWSURFACEDATA
---

# _D3DKMDT_SHADOWSURFACEDATA structure
The D3DKMDT_SHADOWSURFACEDATA structure describes a lockable shadow surface, which matches the primary surface in format and resolution for a given display mode.

## Syntax
```
typedef struct _D3DKMDT_SHADOWSURFACEDATA {
  UINT         Width;
  UINT         Height;
  D3DDDIFORMAT Format;
  UINT         Pitch;
} D3DKMDT_SHADOWSURFACEDATA;
```

## Members


`Width`

[in] The width of the surface, in pixels. The driver returns the width value.

`Height`

[in] The height of the surface, in pixels. The driver returns the height value.

`Format`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the surface. The driver returns the format value.

`Pitch`

[out] The width of the surface, in bytes. The driver must return the pitch value because the shadow surface is lockable.

## Remarks
The D3DKMDT_SHADOWSURFACEDATA structure is passed by the Microsoft DirectX graphics kernel subsystem in a call to the display miniport driver's <a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a> function to generate a description of a lockable shadow surface. The DirectX graphics kernel subsystem uses the description in a call to the display miniport driver's <a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a> function to create the lockable shadow surface.

The CPU draws into the locked shadow surface, unlocks the shadow surface, and then issues bit-block transfer (bitblt) requests through the <a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a> function from the shadow surface to the matched shared primary surface. Bit-block transfer requests are also issued to transfer data from a shared primary surface into the shadow surface. 

A color conversion, stretch, or shrink operation is not required when copying data from or to a shadow surface because the source and destination formats and dimensions of shadow and shared primary surfaces always match.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546589">D3DKMDT_STANDARDALLOCATION_TYPE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557598">DXGKARG_GETSTANDARDALLOCATIONDRIVERDATA</a>



<a href="https://msdn.microsoft.com/a28287d6-4dfa-4db4-92df-bbcd9379a5b2">DxgkDdiCreateAllocation</a>



<a href="https://msdn.microsoft.com/38a9859f-ed9f-41a5-9bf1-c734480499ea">DxgkDdiGetStandardAllocationDriverData</a>



<a href="https://msdn.microsoft.com/1a46b129-1e78-44e6-a609-59eab206692b">DxgkDdiPresent</a>