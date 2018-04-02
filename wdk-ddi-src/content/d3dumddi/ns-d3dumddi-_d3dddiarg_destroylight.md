---
UID: NS:d3dumddi._D3DDDIARG_DESTROYLIGHT
title: "_D3DDDIARG_DESTROYLIGHT"
author: windows-driver-content
description: The D3DDDIARG_DESTROYLIGHT structure contains the index into a light array for the light to destroy.
old-location: display\d3dddiarg_destroylight.htm
old-project: display
ms.assetid: d019a940-5735-4b35-af99-3aac3dc4270b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_DESTROYLIGHT, D3DDDIARG_DESTROYLIGHT structure [Display Devices], UMDisplayDriver_param_Structs_497b7bc8-b2ca-4ead-9c3e-365673b2058f.xml, _D3DDDIARG_DESTROYLIGHT, d3dumddi/D3DDDIARG_DESTROYLIGHT, display.d3dddiarg_destroylight
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
-	D3DDDIARG_DESTROYLIGHT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_DESTROYLIGHT
---

# _D3DDDIARG_DESTROYLIGHT structure
The D3DDDIARG_DESTROYLIGHT structure contains the index into a light array for the light to destroy.

## Syntax
```
typedef struct _D3DDDIARG_DESTROYLIGHT {
  UINT Index;
} D3DDDIARG_DESTROYLIGHT;
```

## Members


`Index`

[in] The index of the light to destroy.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/dbc86e4d-a002-4270-a3c4-02d16972c921">DestroyLight</a>