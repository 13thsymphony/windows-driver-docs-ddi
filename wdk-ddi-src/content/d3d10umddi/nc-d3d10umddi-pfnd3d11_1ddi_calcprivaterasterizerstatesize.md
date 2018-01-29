---
UID : NC:d3d10umddi.PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
title : PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE
author : windows-driver-content
description : Determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a rasterizer state.
old-location : display\calcprivaterasterizerstatesize_d3d11_1_.htm
old-project : display
ms.assetid : 76d0228e-a6e5-425e-a2b6-7d719dbfa43d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.calcprivaterasterizerstatesize_d3d11_1_, CalcPrivateRasterizerStateSize(D3D11_1) callback function [Display Devices], CalcPrivateRasterizerStateSize(D3D11_1), PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE, PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE, d3d10umddi/CalcPrivateRasterizerStateSize(D3D11_1), display.pfncalcprivaterasterizerstatesize
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
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
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1_ddi_rasterizer_desc.md">D3D11_1_DDI_RASTERIZER_DESC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CALCPRIVATERASTERIZERSTATESIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>