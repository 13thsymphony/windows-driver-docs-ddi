---
UID: NC:d3dumddi.PFND3DDDI_SETPIXELSHADERCONSTI
title: PFND3DDDI_SETPIXELSHADERCONSTI
author: windows-driver-content
description: The SetPixelShaderConstI function sets one or more pixel shader constant registers with integer values.
old-location: display\setpixelshaderconsti.htm
old-project: display
ms.assetid: fafc046e-0595-4901-bfb1-70bd980388bc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_SETPIXELSHADERCONSTI, SetPixelShaderConstI, SetPixelShaderConstI callback function [Display Devices], UserModeDisplayDriver_Functions_409d06ae-2fdf-4c27-9f12-abd91a179bcb.xml, d3dumddi/SetPixelShaderConstI, display.setpixelshaderconsti
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
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
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	SetPixelShaderConstI
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_SETPIXELSHADERCONSTI callback function
The <i>SetPixelShaderConstI</i> function sets one or more pixel shader constant registers with integer values.

## Syntax

```
PFND3DDDI_SETPIXELSHADERCONSTI Pfnd3dddiSetpixelshaderconsti;

HRESULT Pfnd3dddiSetpixelshaderconsti(
  HANDLE hDevice,
  CONST D3DDDIARG_SETPIXELSHADERCONSTI *,
  CONST INT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`



`*`




## Return Value

<i>SetPixelShaderConstI</i> returns S_OK or an appropriate error result if the pixel shader constant registers are not successfully set with integer values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff543329">D3DDDIARG_SETPIXELSHADERCONST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>