---
UID: NS:d3dumddi._D3DDDIARG_FLIPOVERLAY
title: "_D3DDDIARG_FLIPOVERLAY"
author: windows-driver-content
description: The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay.
old-location: display\d3dddiarg_flipoverlay.htm
old-project: display
ms.assetid: 36ea4547-e9a0-49c9-8b45-903a2de60923
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_FLIPOVERLAY, D3DDDIARG_FLIPOVERLAY structure [Display Devices], UMDisplayDriver_param_Structs_078e5dd1-bbd8-4067-85a7-2474d18b1d40.xml, _D3DDDIARG_FLIPOVERLAY, d3dumddi/D3DDDIARG_FLIPOVERLAY, display.d3dddiarg_flipoverlay
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
-	d3dumddi.h
api_name:
-	D3DDDIARG_FLIPOVERLAY
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_FLIPOVERLAY
---

# _D3DDDIARG_FLIPOVERLAY structure
The D3DDDIARG_FLIPOVERLAY structure describes a new resource to display on a given overlay.

## Syntax
```
typedef struct _D3DDDIARG_FLIPOVERLAY {
  HANDLE                  hOverlay;
  HANDLE                  hSource;
  UINT                    SourceIndex;
  D3DDDI_FLIPOVERLAYFLAGS Flags;
} D3DDDIARG_FLIPOVERLAY;
```

## Members


`hOverlay`

[in] A handle to the overlay hardware to be flipped.

`hSource`

[in] A handle to the new resource to be displayed. This resource might be the same as the resource that was previously displayed if deinterlacing interleaved data.

`SourceIndex`

[in] The zero-based index of the subresource to be displayed.

`Flags`

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544559">D3DDDI_FLIPOVERLAYFLAGS</a> structure that indicates, in bit-field flags, how to flip the resource.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544559">D3DDDI_FLIPOVERLAYFLAGS</a>



<a href="https://msdn.microsoft.com/8490ebdd-f993-4c77-b6da-d57ef5e5d05f">FlipOverlay</a>