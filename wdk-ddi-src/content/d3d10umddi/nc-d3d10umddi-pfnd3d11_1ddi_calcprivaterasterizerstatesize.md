---
UID: NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
title: PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
author: windows-driver-content
description: Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.
old-location: display\calcprivaterasterizerstatesize_d3d11_1_.htm
old-project: display
ms.assetid: 76d0228e-a6e5-425e-a2b6-7d719dbfa43d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateRasterizerStateSize(D3D11_1), CalcPrivateRasterizerStateSize(D3D11_1) callback function [Display Devices], PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE, d3d10umddi/CalcPrivateRasterizerStateSize(D3D11_1), display.calcprivaterasterizerstatesize_d3d11_1_, display.pfncalcprivaterasterizerstatesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	D3d10umddi.h
api_name:
-	CalcPrivateRasterizerStateSize(D3D11_1)
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE callback function
Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.

## Syntax

```
PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE Pfnd3d111DdiCalcprivaterasterizerstatesize;

SIZE_T Pfnd3d111DdiCalcprivaterasterizerstatesize(
   D3D10DDI_HDEVICE,
  CONST D3D11_1_DDI_RASTERIZER_DESC *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

The size of the memory region that the driver requires for creating a rasterizer state.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451052">D3D11_1_DDI_RASTERIZER_DESC</a>