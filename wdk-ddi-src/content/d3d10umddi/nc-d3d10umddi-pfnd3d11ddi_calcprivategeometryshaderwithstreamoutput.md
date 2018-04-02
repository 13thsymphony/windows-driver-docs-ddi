---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D11DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The CalcPrivateGeometryShaderWithStreamOutput(D3D11) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.
old-location: display\calcprivategeometryshaderwithstreamoutput_d3d11_.htm
old-project: display
ms.assetid: ba3f5a24-c608-42ca-bada-b126cb080f15
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateGeometryShaderWithStreamOutput, CalcPrivateGeometryShaderWithStreamOutput callback function [Display Devices], PFND3D11DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT, UserModeDisplayDriverDx11_Functions_7345bace-3d45-45fe-a0f5-ee76a842c998.xml, d3d10umddi/CalcPrivateGeometryShaderWithStreamOutput, display.calcprivategeometryshaderwithstreamoutput_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateGeometryShaderWithStreamOutput(D3D11) is supported beginning with the Windows 7 operating system.
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
-	CalcPrivateGeometryShaderWithStreamOutput
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function
The <i>CalcPrivateGeometryShaderWithStreamOutput(D3D11)</i> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a geometry shader with stream output.

## Syntax

```
PFND3D11DDI_CALCPRIVATEGEOMETRYSHADERWITHSTREAMOUTPUT Pfnd3d11ddiCalcprivategeometryshaderwithstreamoutput;

SIZE_T Pfnd3d11ddiCalcprivategeometryshaderwithstreamoutput(
   D3D10DDI_HDEVICE,
  CONST D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT *,
  CONST D3D10DDIARG_STAGE_IO_SIGNATURES *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`



`*`




## Return Value

<i>CalcPrivateGeometryShaderWithStreamOutput(D3D11)</i> returns the size of the memory region that the driver requires to create a geometry shader with stream output.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | CalcPrivateGeometryShaderWithStreamOutput(D3D11) is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542057">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>