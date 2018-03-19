---
UID: NC:d3dumddi.PFND3DDDI_DELETEVERTEXSHADERFUNC
title: PFND3DDDI_DELETEVERTEXSHADERFUNC
author: windows-driver-content
description: The DeleteVertexShaderFunc function cleans up driver-side resources that are associated with vertex shader code.
old-location: display\deletevertexshaderfunc.htm
old-project: display
ms.assetid: 780fc47c-bbb9-400a-a2f3-cdce4a18072f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DeleteVertexShaderFunc, DeleteVertexShaderFunc callback function [Display Devices], PFND3DDDI_DELETEVERTEXSHADERFUNC, UserModeDisplayDriver_Functions_fda8f115-6f28-4295-b74e-14f32168a616.xml, d3dumddi/DeleteVertexShaderFunc, display.deletevertexshaderfunc
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
-	DeleteVertexShaderFunc
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_DELETEVERTEXSHADERFUNC callback function
The <b>DeleteVertexShaderFunc</b> function cleans up driver-side resources that are associated with vertex shader code.

## Syntax

```
PFND3DDDI_DELETEVERTEXSHADERFUNC Pfnd3dddiDeletevertexshaderfunc;

HRESULT Pfnd3dddiDeletevertexshaderfunc(
  HANDLE hDevice,
   HANDLE
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`HANDLE`




## Return Value

<b>DeleteVertexShaderFunc</b> returns S_OK or an appropriate error result if the vertex shader code object is not successfully cleaned up.

## Remarks

The <b>DeleteVertexShaderFunc</b> function notifies the driver about the deletion of the vertex shader code object that the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderfunc.md">CreateVertexShaderFunc</a> function created. The driver can then clean up any driver-side resources that are associated with the vertex shader code.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createvertexshaderfunc.md">CreateVertexShaderFunc</a>