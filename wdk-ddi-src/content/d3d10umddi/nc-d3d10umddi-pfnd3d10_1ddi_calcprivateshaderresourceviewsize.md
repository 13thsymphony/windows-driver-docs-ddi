---
UID: NC:d3d10umddi.PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
title: PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
author: windows-driver-content
description: The CalcPrivateShaderResourceViewSize(D3D10_1) function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.
old-location: display\calcprivateshaderresourceviewsize_d3d10_1_.htm
old-project: display
ms.assetid: 310adb3e-1af4-430e-ba50-bd145ffda361
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivateshaderresourceviewsize_d3d10_1_, CalcPrivateShaderResourceViewSize_d3d10_1_ callback function [Display Devices], CalcPrivateShaderResourceViewSize_d3d10_1_, PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE, d3d10umddi/CalcPrivateShaderResourceViewSize_d3d10_1_, UserModeDisplayDriverDx10_Functions_dc420977-d68c-4e07-b134-fc5540a96e7b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: CalcPrivateShaderResourceViewSize(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions.
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
-	CalcPrivateShaderResourceViewSize_d3d10_1_
product: Windows
targetos: Windows
req.typenames: "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function
The <b>CalcPrivateShaderResourceViewSize(D3D10_1)</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.

## Syntax

```
PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE Pfnd3d101DdiCalcprivateshaderresourceviewsize;

SIZE_T Pfnd3d101DdiCalcprivateshaderresourceviewsize(
   D3D10DDI_HDEVICE,
  CONST D3D10_1DDIARG_CREATESHADERRESOURCEVIEW *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateShaderResourceViewSize(D3D10_1)</b> returns the size of the memory region that the driver requires for creating a shader resource view.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | CalcPrivateShaderResourceViewSize(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions. CalcPrivateShaderResourceViewSize(D3D10_1) is supported on Windows Vista with Service Pack 1 (SP1) and later versions and Windows Server 2008 and later versions. |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddiarg_createshaderresourceview.md">D3D10_1DDIARG_CREATESHADERRESOURCEVIEW</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d10_1ddi_devicefuncs.md">D3D10_1DDI_DEVICEFUNCS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10_1DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>