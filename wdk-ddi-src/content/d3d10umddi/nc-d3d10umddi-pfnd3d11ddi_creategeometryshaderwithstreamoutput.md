---
UID: NC:d3d10umddi.PFND3D11DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
title: PFND3D11DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT
author: windows-driver-content
description: The CreateGeometryShaderWithStreamOutput(D3D11) function creates a geometry shader with stream output.
old-location: display\creategeometryshaderwithstreamoutput_d3d11_.htm
old-project: display
ms.assetid: 86970ea4-e7d2-4fc3-9f97-75a946a21a17
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateGeometryShaderWithStreamOutput, CreateGeometryShaderWithStreamOutput callback function [Display Devices], PFND3D11DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT, UserModeDisplayDriverDx11_Functions_65b14f27-0df8-421d-95bb-f8a4ebc7c1c1.xml, d3d10umddi/CreateGeometryShaderWithStreamOutput, display.creategeometryshaderwithstreamoutput_d3d11_
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CreateGeometryShaderWithStreamOutput(D3D11) is supported beginning with the Windows 7 operating system.
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
-	CreateGeometryShaderWithStreamOutput
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT callback function
The <b>CreateGeometryShaderWithStreamOutput(D3D11)</b> function creates a geometry shader with stream output.

## Syntax

```
PFND3D11DDI_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT Pfnd3d11ddiCreategeometryshaderwithstreamoutput;

void Pfnd3d11ddiCreategeometryshaderwithstreamoutput(
   D3D10DDI_HDEVICE,
  CONST D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT *,
   D3D10DDI_HSHADER,
   D3D10DDI_HRTSHADER,
  CONST D3D10DDIARG_STAGE_IO_SIGNATURES *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`



`D3D10DDI_HSHADER`



`D3D10DDI_HRTSHADER`



`*`




## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

The driver can pass E_OUTOFMEMORY (if the driver runs out of memory) or D3DDDIERR_DEVICEREMOVED (if the device is removed) in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the <a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a> function to destroy the handle that the <i>hShader</i> parameter specifies.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | CreateGeometryShaderWithStreamOutput(D3D11) is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/ba3f5a24-c608-42ca-bada-b126cb080f15">CalcPrivateGeometryShaderWithStreamOutput(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541746">D3D10DDIARG_STAGE_IO_SIGNATURES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542057">D3D11DDIARG_CREATEGEOMETRYSHADERWITHSTREAMOUTPUT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff542141">D3D11DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/51a3e5aa-0f17-49a6-824d-7cfe8e0a1ded">DestroyShader</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>