---
UID: NS:d3dhal._D3DHAL_DP2COMMAND
title: "_D3DHAL_DP2COMMAND"
author: windows-driver-content
description: One or more D3DHAL_DP2COMMAND structures are parsed from the command buffer by the D3dDrawPrimitives2 callback, which uses the information it receives to draw one or more primitives.
old-location: display\d3dhal_dp2command.htm
old-project: display
ms.assetid: 3fa32e5c-32d5-4e26-82b5-45dbf5389f2b
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*LPD3DHAL_DP2COMMAND, D3DHAL_DP2COMMAND, D3DHAL_DP2COMMAND structure [Display Devices], LPD3DHAL_DP2COMMAND, LPD3DHAL_DP2COMMAND structure pointer [Display Devices], _D3DHAL_DP2COMMAND, d3dhal/D3DHAL_DP2COMMAND, d3dhal/LPD3DHAL_DP2COMMAND, d3dstrct_9497e802-c325-4d08-ba6c-f482d17da6c5.xml, display.d3dhal_dp2command"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
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
-	d3dhal.h
api_name:
-	D3DHAL_DP2COMMAND
product:
- Windows
targetos: Windows
req.typenames: D3DHAL_DP2COMMAND, *LPD3DHAL_DP2COMMAND
---

# _D3DHAL_DP2COMMAND structure
One or more D3DHAL_DP2COMMAND structures are parsed from the command buffer by the <a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a> callback, which uses the information it receives to draw one or more primitives. Each structure specifies either a primitive to draw or a state change to process.

## Syntax
```
typedef struct _D3DHAL_DP2COMMAND {
  BYTE  bCommand;
  BYTE  bReserved;
  union {
    WORD wPrimitiveCount;
    WORD wStateCount;
  };
} D3DHAL_DP2COMMAND, *LPD3DHAL_DP2COMMAND;
```

## Members


`bCommand`

Specifies a primitive to draw or a state change to process. This member can be one of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545678">D3DHAL_DP2OPERATION</a> enumerated values.

`bReserved`

Reserved for system use and should be ignored by the driver.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3dhal.h (include D3dhal.h) |

## See Also

D3DDP2OP_RENDERSTATE



D3DDP2OP_TEXTURESTAGESTATE



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545678">D3DHAL_DP2OPERATION</a>



<a href="https://msdn.microsoft.com/6128ff7a-0d2c-48df-8b5e-cab33c5a74f5">D3dDrawPrimitives2</a>