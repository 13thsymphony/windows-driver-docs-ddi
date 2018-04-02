---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATERESOURCESIZE
title: PFND3D10DDI_CALCPRIVATERESOURCESIZE
author: windows-driver-content
description: The CalcPrivateResourceSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).
old-location: display\calcprivateresourcesize.htm
old-project: display
ms.assetid: 2c4eb002-4788-46ab-92b9-3bb2dcb44ee3
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CalcPrivateResourceSize, CalcPrivateResourceSize callback function [Display Devices], PFND3D10DDI_CALCPRIVATERESOURCESIZE, UserModeDisplayDriverDx10_Functions_bc7bb9a2-6fe2-49fb-b7d2-81297a828418.xml, d3d10umddi/CalcPrivateResourceSize, display.calcprivateresourcesize
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
-	CalcPrivateResourceSize
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CALCPRIVATERESOURCESIZE callback function
The <b>CalcPrivateResourceSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory).

## Syntax

```
PFND3D10DDI_CALCPRIVATERESOURCESIZE Pfnd3d10ddiCalcprivateresourcesize;

SIZE_T Pfnd3d10ddiCalcprivateresourcesize(
   D3D10DDI_HDEVICE,
  CONST D3D10DDIARG_CREATERESOURCE *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateResourceSize</b> returns the size of the memory region that the driver requires for creating resources.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>