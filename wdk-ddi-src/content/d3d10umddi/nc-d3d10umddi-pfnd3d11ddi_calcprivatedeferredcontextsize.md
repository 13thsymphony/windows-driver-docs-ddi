---
UID: NC:d3d10umddi.PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE
title: PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE
author: windows-driver-content
description: The CalcPrivateDeferredContextSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a deferred context.
old-location: display\calcprivatedeferredcontextsize.htm
old-project: display
ms.assetid: 282898b1-45e1-4d85-9ab7-fd400623bdc5
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateDeferredContextSize, CalcPrivateDeferredContextSize callback function [Display Devices], PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE, UserModeDisplayDriverDx11_Functions_577f34a4-1f2e-4666-8bce-00dc6e52c2e6.xml, d3d10umddi/CalcPrivateDeferredContextSize, display.calcprivatedeferredcontextsize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateDeferredContextSize is supported beginning with the Windows 7 operating system.
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
-	CalcPrivateDeferredContextSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE callback function
The <b>CalcPrivateDeferredContextSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a deferred context.

## Syntax

```
PFND3D11DDI_CALCPRIVATEDEFERREDCONTEXTSIZE Pfnd3d11ddiCalcprivatedeferredcontextsize;

SIZE_T Pfnd3d11ddiCalcprivatedeferredcontextsize(
   D3D10DDI_HDEVICE,
  CONST D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateDeferredContextSize</b> returns the size of the memory region that the driver requires to create a deferred context.

## Remarks

The driver is only required to implement <b>CalcPrivateDeferredContextSize</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | CalcPrivateDeferredContextSize is supported beginning with the Windows 7 operating system.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddiarg_calcprivatedeferredcontextsize.md">D3D11DDIARG_CALCPRIVATEDEFERREDCONTEXTSIZE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10_2ddi_getcaps.md">GetCaps(D3D10_2)</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>