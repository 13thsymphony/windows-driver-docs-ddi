---
UID: NS:d3d10umddi.D3D10_DDI_BOX
title: D3D10_DDI_BOX
author: windows-driver-content
description: The D3D10_DDI_BOX structure describes a volume.
old-location: display\d3d10_ddi_box.htm
old-project: display
ms.assetid: b09ea915-070d-4ebb-a40d-d60add5df3d8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3D10_DDI_BOX, D3D10_DDI_BOX structure [Display Devices], UMDisplayDriver_Dx10param_Structs_11ac8e3e-48db-469b-a6e6-d42fd491d56e.xml, d3d10umddi/D3D10_DDI_BOX, display.d3d10_ddi_box
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	D3D10_DDI_BOX
product: Windows
targetos: Windows
req.typenames: D3D10_DDI_BOX
---

# D3D10_DDI_BOX structure
The D3D10_DDI_BOX structure describes a volume.

## Syntax
````
typedef struct D3D10_DDI_BOX {
  LONG left;
  LONG top;
  LONG front;
  LONG right;
  LONG bottom;
  LONG back;
} D3D10_DDI_BOX;
````

## Members


`left`

[in] The position of the left side of the box on the x-axis.

`top`

[in] The position of the top of the box on the y-axis.

`front`

[in] The position of the front of the box on the z-axis.

`right`

[in] The position of the right side of the box on the x-axis. Note that the width of the volume equals the value in the <b>right</b> member minus the value in the <b>left</b> member (that is, width = right – left).

`bottom`

[in] The position of the bottom of the box on the y-axis. Note that the height of the volume equals the value in the <b>bottom</b> member minus the value in the <b>top</b> member (that is, height = bottom – top).

`back`

[in] The position of the back of the box on the z-axis. Note that the depth of the volume equals the value in the <b>back</b> member minus the value in the <b>front</b> member (that is, depth = back – front).


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_resourcecopyregion.md">ResourceCopyRegion</a>