---
UID: NC:d3dumddi.PFND3DDDI_CREATEVERTEXSHADERFUNC
title: PFND3DDDI_CREATEVERTEXSHADERFUNC
author: windows-driver-content
description: The CreateVertexShaderFunc function converts vertex shader code into a hardware-specific format and associates the code with a shader handle.
old-location: display\createvertexshaderfunc.htm
old-project: display
ms.assetid: e986d37a-6039-4bc4-b5e8-6c4d4d7adedd
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateVertexShaderFunc, CreateVertexShaderFunc callback function [Display Devices], PFND3DDDI_CREATEVERTEXSHADERFUNC, UserModeDisplayDriver_Functions_bb697f1f-765f-46d9-961a-f4e8060727bc.xml, d3dumddi/CreateVertexShaderFunc, display.createvertexshaderfunc
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
-	CreateVertexShaderFunc
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CREATEVERTEXSHADERFUNC callback function
The <b>CreateVertexShaderFunc</b> function converts vertex shader code into a hardware-specific format and associates the code with a shader handle.

## Syntax

```
PFND3DDDI_CREATEVERTEXSHADERFUNC Pfnd3dddiCreatevertexshaderfunc;

HRESULT Pfnd3dddiCreatevertexshaderfunc(
  HANDLE hDevice,
  D3DDDIARG_CREATEVERTEXSHADERFUNC *,
  CONST UINT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`



`*`




## Return Value

<b>CreateVertexShaderFunc</b> returns S_OK or an appropriate error result if the vertex shader code object is not successfully created.

## Remarks

For more information about programming shader assemblers, see <a href="https://msdn.microsoft.com/c858766c-b414-4971-b4d9-23ec94aca8ea">Processing Shader Codes</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff542973">D3DDDIARG_CREATEVERTEXSHADERFUNC</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff544519">D3DDDI_DEVICEFUNCS</a>