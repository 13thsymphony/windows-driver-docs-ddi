---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_SCALE_SUPPORT_0022
title: D3D12DDI_VIDEO_SCALE_SUPPORT_0022
author: windows-driver-content
description: Describes a supported range of output sizes for a scaler.
old-location: display\d3d12ddi_video_scale_support.htm
old-project: display
ms.assetid: 70FFDE9E-2029-4C84-9DEE-C2E81FEE5590
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D12DDI_VIDEO_SCALE_SUPPORT_0022, D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure [Display Devices], d3d12umddi/D3D12DDI_VIDEO_SCALE_SUPPORT_0022, display.d3d12ddi_video_scale_support
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3d12umddi.h
api_name:
-	D3D12DDI_VIDEO_SCALE_SUPPORT_0022
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_SCALE_SUPPORT_0022
---

# D3D12DDI_VIDEO_SCALE_SUPPORT_0022 structure
Describes a supported range of output sizes for a scaler.

## Syntax
````
typedef struct D3D12DDI_VIDEO_SCALE_SUPPORT_0022 {
  UINT                                    MaxOutputWidth;
  UINT                                    MaxOutputHeight;
  UINT                                    MinOutputWidth;
  UINT                                    MinOutputHeight;
  D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS_0022 ScaleSupportFlags;
} D3D12DDI_VIDEO_SCALE_SUPPORT_0022;
````

## Members


`MaxOutputWidth`

The largest output width that can be scaled to.  The largest value allowed is <b>D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION</b>, which is 16384.

`MaxOutputHeight`

The largest output height that can be scaled to.  The largest value allowed is <b>D3D12_REQ_TEXTURE2D_U_OR_V_DIMENSION</b>, which is 16384.

`MinOutputWidth`

The smallest output width that can be scaled to.  The smallest allowed value is 1.

`MinOutputHeight`

The smallest output height that can be scaled to.  The smallest allowed value is 1.

`Flags`



## Remarks
By default, supported indicates that all possible output size combinations that exist between the maximum  size and minimum size for the extent, inclusive, are supported.  The values in the <i>ScaleSupportFlags</i> value may add additional restrictions.


When scaling is not supported, the maximum and maximum sizes should both be set to the input size and no flags specified.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |

## See Also

<a href="..\d3d12umddi\ne-d3d12umddi-d3d12ddi_video_scale_support_flags_0022.md">D3D12DDI_VIDEO_SCALE_SUPPORT_FLAGS</a>