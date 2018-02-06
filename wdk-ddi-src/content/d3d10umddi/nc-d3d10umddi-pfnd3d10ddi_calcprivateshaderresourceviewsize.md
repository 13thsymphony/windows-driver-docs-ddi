---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
author: windows-driver-content
description: The CalcPrivateShaderResourceViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize.htm
old-project: display
ms.assetid: 2abf5ca9-974b-40d7-b71c-43c4fb33dd7c
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivateshaderresourceviewsize, CalcPrivateShaderResourceViewSize callback function [Display Devices], CalcPrivateShaderResourceViewSize, PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, d3d10umddi/CalcPrivateShaderResourceViewSize, UserModeDisplayDriverDx10_Functions_57360213-38f5-45aa-aadb-0bcdb674aec1.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	d3d10umddi.h
apiname:
-	CalcPrivateShaderResourceViewSize
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
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
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createshaderresourceview.md">D3D10DDIARG_CREATESHADERRESOURCEVIEW</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>