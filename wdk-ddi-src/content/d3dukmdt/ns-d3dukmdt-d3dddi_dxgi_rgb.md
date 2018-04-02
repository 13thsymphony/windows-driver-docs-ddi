---
UID: NS:d3dukmdt.D3DDDI_DXGI_RGB
title: D3DDDI_DXGI_RGB
author: windows-driver-content
description: The D3DDDI_DXGI_RGB structure contains information to describe a gamma function.
old-location: display\d3dddi_dxgi_rgb.htm
old-project: display
ms.assetid: 4bf25ae0-30fa-49a6-a5a8-c807e14d9857
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDI_DXGI_RGB, D3DDDI_DXGI_RGB structure [Display Devices], DmStructs_808243de-342c-439b-9ebe-d418ccedd8ff.xml, d3dukmdt/D3DDDI_DXGI_RGB, display.d3dddi_dxgi_rgb
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
-	D3DDDI_DXGI_RGB
product:
- Windows
targetos: Windows
req.typenames: D3DDDI_DXGI_RGB
---

# D3DDDI_DXGI_RGB structure
The D3DDDI_DXGI_RGB structure contains information to describe a gamma function.

## Syntax
```
typedef struct D3DDDI_DXGI_RGB {
  float Red;
  float Green;
  float Blue;
};
```

## Members


`Red`

A FLOAT value that is used to describe the gamma function for the red color channel.

`Green`

A FLOAT value that is used to describe the gamma function for the green color channel.

`Blue`

A FLOAT value that is used to describe the gamma function for the blue color channel.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dukmdt.h (include D3dukmdt.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544568">D3DDDI_GAMMA_RAMP_DXGI_1</a>