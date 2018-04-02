---
UID: NS:d3dumddi._D3DDDIARG_DESTROYOVERLAY
title: "_D3DDDIARG_DESTROYOVERLAY"
author: windows-driver-content
description: The D3DDDIARG_DESTROYOVERLAY structure contains a handle to the overlay to disable.
old-location: display\d3dddiarg_destroyoverlay.htm
old-project: display
ms.assetid: a468205c-288c-49d5-ab14-0ee39dca7b7c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_DESTROYOVERLAY, D3DDDIARG_DESTROYOVERLAY structure [Display Devices], UMDisplayDriver_param_Structs_e7a2d82a-2e1c-4362-ae4d-23617911de3b.xml, _D3DDDIARG_DESTROYOVERLAY, d3dumddi/D3DDDIARG_DESTROYOVERLAY, display.d3dddiarg_destroyoverlay
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
-	D3DDDIARG_DESTROYOVERLAY
product:
- Windows
targetos: Windows
req.typenames: D3DDDIARG_DESTROYOVERLAY
---

# _D3DDDIARG_DESTROYOVERLAY structure
The D3DDDIARG_DESTROYOVERLAY structure contains a handle to the overlay to disable.

## Syntax
```
typedef struct _D3DDDIARG_DESTROYOVERLAY {
  HANDLE hOverlay;
} D3DDDIARG_DESTROYOVERLAY;
```

## Members


`hOverlay`

[in] A handle to the overlay to disable.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/63004d19-e2cd-462c-8fa5-ea4dd6e29735">DestroyOverlay</a>