---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE
title: PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE
author: windows-driver-content
description: The CalcPrivateTessellationShaderSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a hull or domain shader.
old-location: display\calcprivatetessellationshadersize.htm
old-project: display
ms.assetid: 604d7475-4696-429e-a645-781931509bb6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateTessellationShaderSize, CalcPrivateTessellationShaderSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE, UserModeDisplayDriverDx11_Functions_a669f28f-b275-4265-b6ae-5c3526d81b46.xml, d3d10umddi/CalcPrivateTessellationShaderSize, display.calcprivatetessellationshadersize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateTessellationShaderSize is supported beginning with the Windows 7 operating system.
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
-	d3d10umddi.h
api_name:
-	CalcPrivateTessellationShaderSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE callback function
The <b>CalcPrivateTessellationShaderSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a hull or domain shader.

## Syntax

```
PFND3D11DDI_CALCPRIVATETESSELLATIONSHADERSIZE Pfnd3d11ddiCalcprivatetessellationshadersize;

SIZE_T Pfnd3d11ddiCalcprivatetessellationshadersize(
   D3D10DDI_HDEVICE,
  CONST UINT *pShaderCode,
  CONST D3D11DDIARG_TESSELLATION_IO_SIGNATURES *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*pShaderCode`



`*`




## Return Value

<b>CalcPrivateTessellationShaderSize</b> returns the size of the memory region that the driver requires to create a hull or domain shader.

## Remarks

The Direct3D runtime calls the driver's <b>CalcPrivateTessellationShaderSize</b> function to calculate the size of the memory region for a hull or domain shader. This is similar to the way that the Direct3D runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize.md">CalcPrivateShaderSize</a> function to calculate the size of the memory region for a pixel, vertex, or geometry shader (that is, a geometry shader without stream output).

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | CalcPrivateTessellationShaderSize is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_calcprivateshadersize.md">CalcPrivateShaderSize</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_tessellation_io_signatures.md">D3D11DDIARG_TESSELLATION_IO_SIGNATURES</a>