---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
author: windows-driver-content
description: The CalcPrivateShaderResourceViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize.htm
old-project: display
ms.assetid: 2abf5ca9-974b-40d7-b71c-43c4fb33dd7c
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateShaderResourceViewSize, CalcPrivateShaderResourceViewSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, UserModeDisplayDriverDx10_Functions_57360213-38f5-45aa-aadb-0bcdb674aec1.xml, d3d10umddi/CalcPrivateShaderResourceViewSize, display.calcprivateshaderresourceviewsize
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
-	CalcPrivateShaderResourceViewSize
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function
The <b>CalcPrivateShaderResourceViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.

## Syntax

```
PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE Pfnd3d10ddiCalcprivateshaderresourceviewsize;

SIZE_T Pfnd3d10ddiCalcprivateshaderresourceviewsize(
   D3D10DDI_HDEVICE,
  CONST D3D10DDIARG_CREATESHADERRESOURCEVIEW *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateShaderResourceViewSize</b> returns the size of the memory region that the driver requires for creating a shader resource view.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541708">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>