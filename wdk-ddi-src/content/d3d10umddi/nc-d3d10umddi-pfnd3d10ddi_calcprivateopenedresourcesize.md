---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE
title: PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE
author: windows-driver-content
description: The CalcPrivateOpenedResourceSize function determines the size of the user-mode display driver's private shared region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an opened resource.
old-location: display\calcprivateopenedresourcesize.htm
old-project: display
ms.assetid: 000688fb-6475-4dab-bb65-91c899a592a7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CalcPrivateOpenedResourceSize, CalcPrivateOpenedResourceSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE, UserModeDisplayDriverDx10_Functions_1be7ba80-5ffc-4871-b687-f12b4a81fad0.xml, d3d10umddi/CalcPrivateOpenedResourceSize, display.calcprivateopenedresourcesize
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
-	CalcPrivateOpenedResourceSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE callback function
The <b>CalcPrivateOpenedResourceSize</b> function determines the size of the user-mode display driver's private shared region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an opened resource.

## Syntax

```
PFND3D10DDI_CALCPRIVATEOPENEDRESOURCESIZE Pfnd3d10ddiCalcprivateopenedresourcesize;

SIZE_T Pfnd3d10ddiCalcprivateopenedresourcesize(
   D3D10DDI_HDEVICE,
  CONST D3D10DDIARG_OPENRESOURCE *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateOpenedResourceSize</b> returns the size of the shared memory region that the driver requires for opening resources.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_openresource.md">D3D10DDIARG_OPENRESOURCE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>