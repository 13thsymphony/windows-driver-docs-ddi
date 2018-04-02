---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE
title: PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE
author: windows-driver-content
description: The CalcPrivateRenderTargetViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a render target view.
old-location: display\calcprivaterendertargetviewsize.htm
old-project: display
ms.assetid: 14d85e4a-960c-4438-9360-a4f2677603b8
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateRenderTargetViewSize, CalcPrivateRenderTargetViewSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE, UserModeDisplayDriverDx10_Functions_48ca8f95-06ba-4a11-8517-bd4638691e65.xml, d3d10umddi/CalcPrivateRenderTargetViewSize, display.calcprivaterendertargetviewsize
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
-	CalcPrivateRenderTargetViewSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE callback function
The <b>CalcPrivateRenderTargetViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a render target view.

## Syntax

```
PFND3D10DDI_CALCPRIVATERENDERTARGETVIEWSIZE Pfnd3d10ddiCalcprivaterendertargetviewsize;

SIZE_T Pfnd3d10ddiCalcprivaterendertargetviewsize(
   D3D10DDI_HDEVICE,
  CONST D3D10DDIARG_CREATERENDERTARGETVIEW *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateRenderTargetViewSize</b> returns the size of the memory region that the driver requires for creating a render target view.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541689">D3D10DDIARG_CREATERENDERTARGETVIEW</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>