---
UID: NS:d3dumddi._D3DDDIARG_ZRANGE
title: "_D3DDDIARG_ZRANGE"
author: windows-driver-content
description: The D3DDDIARG_ZRANGE structure specifies z-range minimum and maximum values.
old-location: display\d3dddiarg_zrange.htm
old-project: display
ms.assetid: 710683e7-f628-4baa-b485-75b481812b97
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_ZRANGE, D3DDDIARG_ZRANGE structure [Display Devices], UMDisplayDriver_param_Structs_e1184f4e-5bff-4bdc-bf7a-473039a66ff7.xml, _D3DDDIARG_ZRANGE, d3dumddi/D3DDDIARG_ZRANGE, display.d3dddiarg_zrange
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
-	D3DDDIARG_ZRANGE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_ZRANGE
---

# _D3DDDIARG_ZRANGE structure
The D3DDDIARG_ZRANGE structure specifies z-range minimum and maximum values.

## Syntax
```
typedef struct _D3DDDIARG_ZRANGE {
  FLOAT MinZ;
  FLOAT MaxZ;
} D3DDDIARG_ZRANGE;
```

## Members


`MinZ`

[in] A FLOAT value that indicates the minimum z value for the range.

`MaxZ`

[in] A FLOAT value that indicates the maximum z value for the range.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/29ccde7c-801c-4e90-bc39-8581f262cc65">SetZRange</a>