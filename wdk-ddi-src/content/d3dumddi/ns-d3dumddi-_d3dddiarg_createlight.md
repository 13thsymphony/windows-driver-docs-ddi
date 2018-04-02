---
UID: NS:d3dumddi._D3DDDIARG_CREATELIGHT
title: "_D3DDDIARG_CREATELIGHT"
author: windows-driver-content
description: The D3DDDIARG_CREATELIGHT structure contains the index into the light array.
old-location: display\d3dddiarg_createlight.htm
old-project: display
ms.assetid: 14dcff4a-3295-435b-a1b2-f3aa15117673
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_CREATELIGHT, D3DDDIARG_CREATELIGHT structure [Display Devices], UMDisplayDriver_param_Structs_683ae423-2e77-49e2-8028-3980a2f1a32d.xml, _D3DDDIARG_CREATELIGHT, d3dumddi/D3DDDIARG_CREATELIGHT, display.d3dddiarg_createlight
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
-	D3DDDIARG_CREATELIGHT
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_CREATELIGHT
---

# _D3DDDIARG_CREATELIGHT structure
The D3DDDIARG_CREATELIGHT structure contains the index into the light array.

## Syntax
```
typedef struct _D3DDDIARG_CREATELIGHT {
  UINT Index;
} D3DDDIARG_CREATELIGHT;
```

## Members


`Index`

[in] The index of the light to create.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/4649b1d1-6fd3-48fb-b25f-1228851bb682">CreateLight</a>