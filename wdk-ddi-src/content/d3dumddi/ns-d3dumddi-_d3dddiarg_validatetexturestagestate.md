---
UID: NS:d3dumddi._D3DDDIARG_VALIDATETEXTURESTAGESTATE
title: "_D3DDDIARG_VALIDATETEXTURESTAGESTATE"
author: windows-driver-content
description: The D3DDDIARG_VALIDATETEXTURESTAGESTATE structure contains the number of passes in which the hardware can perform the blending operations that are specified in the current state.
old-location: display\d3dddiarg_validatetexturestagestate.htm
old-project: display
ms.assetid: 28d2efa5-a7bf-4b85-a0f3-a4bad705a874
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: D3DDDIARG_VALIDATETEXTURESTAGESTATE, D3DDDIARG_VALIDATETEXTURESTAGESTATE structure [Display Devices], UMDisplayDriver_param_Structs_dde6cce2-f21e-4a16-8238-6956d9a465f5.xml, _D3DDDIARG_VALIDATETEXTURESTAGESTATE, d3dumddi/D3DDDIARG_VALIDATETEXTURESTAGESTATE, display.d3dddiarg_validatetexturestagestate
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
-	D3DDDIARG_VALIDATETEXTURESTAGESTATE
product: Windows
targetos: Windows
req.typenames: D3DDDIARG_VALIDATETEXTURESTAGESTATE
---

# _D3DDDIARG_VALIDATETEXTURESTAGESTATE structure
The D3DDDIARG_VALIDATETEXTURESTAGESTATE structure contains the number of passes in which the hardware can perform the blending operations that are specified in the current state.

## Syntax
```
typedef struct _D3DDDIARG_VALIDATETEXTURESTAGESTATE {
  UINT NumPasses;
} D3DDDIARG_VALIDATETEXTURESTAGESTATE;
```

## Members


`NumPasses`

[in] The number of passes in which the hardware can perform the blending operations that are specified in the current state.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/058696e0-be4a-45f3-b3e8-55abccdce3ce">ValidateDevice</a>