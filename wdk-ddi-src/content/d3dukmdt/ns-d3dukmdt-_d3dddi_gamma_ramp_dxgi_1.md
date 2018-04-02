---
UID: NS:d3dukmdt._D3DDDI_GAMMA_RAMP_DXGI_1
title: "_D3DDDI_GAMMA_RAMP_DXGI_1"
author: windows-driver-content
description: The D3DDDI_GAMMA_RAMP_DXGI_1 structure describes a gamma function.
old-location: display\d3dddi_gamma_ramp_dxgi_1.htm
old-project: display
ms.assetid: f5c67404-3baf-44f1-8b19-f099cf71c178
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_GAMMA_RAMP_DXGI_1, D3DDDI_GAMMA_RAMP_DXGI_1 structure [Display Devices], DmStructs_378e6432-010f-453c-8e59-d32f243543f0.xml, _D3DDDI_GAMMA_RAMP_DXGI_1, d3dukmdt/D3DDDI_GAMMA_RAMP_DXGI_1, display.d3dddi_gamma_ramp_dxgi_1
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dukmdt.h
req.include-header: D3dukmdt.h
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
-	d3dukmdt.h
api_name:
-	D3DDDI_GAMMA_RAMP_DXGI_1
product: Windows
targetos: Windows
req.typenames: D3DDDI_GAMMA_RAMP_DXGI_1
---

# _D3DDDI_GAMMA_RAMP_DXGI_1 structure
The D3DDDI_GAMMA_RAMP_DXGI_1 structure describes a gamma function.

## Syntax
```
typedef struct _D3DDDI_GAMMA_RAMP_DXGI_1 {
  D3DDDI_DXGI_RGB Scale;
  D3DDDI_DXGI_RGB Offset;
  D3DDDI_DXGI_RGB GammaCurve[1025];
} D3DDDI_GAMMA_RAMP_DXGI_1;
```

## Members


`Scale`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544533">D3DDDI_DXGI_RGB</a> structure that holds the scale for the gamma function.

`Offset`

A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544533">D3DDDI_DXGI_RGB</a> structure that holds the offset for the gamma function.

`GammaCurve`

An array of <a href="https://msdn.microsoft.com/library/windows/hardware/ff544533">D3DDDI_DXGI_RGB</a> structures that describe the curve of the gamma function.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dukmdt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544533">D3DDDI_DXGI_RGB</a>