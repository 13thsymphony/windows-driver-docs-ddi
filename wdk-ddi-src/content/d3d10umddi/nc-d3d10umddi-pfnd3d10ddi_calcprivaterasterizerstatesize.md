---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATERASTERIZERSTATESIZE
title: PFND3D10DDI_CALCPRIVATERASTERIZERSTATESIZE
author: windows-driver-content
description: The CalcPrivateRasterizerStateSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.
old-location: display\calcprivaterasterizerstatesize.htm
old-project: display
ms.assetid: 8b10b2b8-21b0-451c-9a85-353222d9c288
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateRasterizerStateSize, CalcPrivateRasterizerStateSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATERASTERIZERSTATESIZE, UserModeDisplayDriverDx10_Functions_b5ff2557-347f-4cf5-962b-f41b097de388.xml, d3d10umddi/CalcPrivateRasterizerStateSize, display.calcprivaterasterizerstatesize
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
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
-	d3d10umddi.h
api_name:
-	CalcPrivateRasterizerStateSize
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CALCPRIVATERASTERIZERSTATESIZE callback function
The <b>CalcPrivateRasterizerStateSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.

## Syntax

```
PFND3D10DDI_CALCPRIVATERASTERIZERSTATESIZE Pfnd3d10ddiCalcprivaterasterizerstatesize;

SIZE_T Pfnd3d10ddiCalcprivaterasterizerstatesize(
   D3D10DDI_HDEVICE,
  CONST D3D10_DDI_RASTERIZER_DESC *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateRasterizerStateSize</b> returns the size of the memory region that the driver requires for creating a rasterizer state.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541988">D3D10_DDI_RASTERIZER_DESC</a>