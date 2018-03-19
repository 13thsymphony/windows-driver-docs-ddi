---
UID: NS:d3dkmdt._D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
title: "_D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES"
author: windows-driver-content
description: The D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES contains values that indicate the dynamic range of each color channel of a video present target or a monitor.
old-location: display\d3dkmdt_color_coeff_dynamic_ranges.htm
old-project: display
ms.assetid: 7fdd1d52-c406-4da7-adff-4300e795be00
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES, D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure [Display Devices], DmStructs_33f2d82d-dbb3-4d51-bc3c-5c8e334d5113.xml, _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES, d3dkmdt/D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES, display.d3dkmdt_color_coeff_dynamic_ranges
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
-	D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
product: Windows
targetos: Windows
req.typenames: D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES
---

# _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure
The D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES contains values that indicate the dynamic range of each color channel of a video present target or a monitor.

## Syntax
````
typedef struct _D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES {
  UINT FirstChannel;
  UINT SecondChannel;
  UINT ThirdChannel;
  UINT FourthChannel;
} D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES;
````

## Members


`FirstChannel`

The bit depth of the first color channel.

`SecondChannel`

The bit depth of the second color channel.

`ThirdChannel`

The bit depth of the third color channel.

`FourthChannel`

Reserved.

## Remarks
The <b>VidPnTargetColorCoeffDynamicRanges</b> member of the <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dkmdt.h (include D3dkmdt.h) |

## See Also

<a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_color_basis.md">D3DKMDT_COLOR_BASIS</a>