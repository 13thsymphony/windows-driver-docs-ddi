---
UID: NS:d3dumddi._D3DDDIARG_UPDATEOVERLAY
title: "_D3DDDIARG_UPDATEOVERLAY"
author: windows-driver-content
description: The D3DDDIARG_UPDATEOVERLAY structure describes an overlay to modify.
old-location: display\d3dddiarg_updateoverlay.htm
old-project: display
ms.assetid: e49f48fd-f2e8-4ccc-813f-f624e06ab365
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DDDIARG_UPDATEOVERLAY, D3DDDIARG_UPDATEOVERLAY structure [Display Devices], UMDisplayDriver_param_Structs_6c415566-a5f5-4efc-820b-7eb466b59149.xml, _D3DDDIARG_UPDATEOVERLAY, d3dumddi/D3DDDIARG_UPDATEOVERLAY, display.d3dddiarg_updateoverlay
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
-	D3DDDIARG_UPDATEOVERLAY
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_UPDATEOVERLAY
---

# _D3DDDIARG_UPDATEOVERLAY structure
The D3DDDIARG_UPDATEOVERLAY structure describes an overlay to modify.

## Syntax
````
typedef struct _D3DDDIARG_UPDATEOVERLAY {
  HANDLE             hOverlay;
  D3DDDI_OVERLAYINFO OverlayInfo;
} D3DDDIARG_UPDATEOVERLAY;
````

## Members


`hOverlay`

[in] A handle to the overlay to modify.

`OverlayInfo`

[in] A pointer to the <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlayinfo.md">D3DDDI_OVERLAYINFO</a> structure that describes the modification for the overlay.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updateoverlay.md">UpdateOverlay</a>



<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_overlayinfo.md">D3DDDI_OVERLAYINFO</a>