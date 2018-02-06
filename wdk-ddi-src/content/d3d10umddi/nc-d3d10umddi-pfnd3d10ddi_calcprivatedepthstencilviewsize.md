---
UID: NC:d3d10umddi.PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
title: PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE
author: windows-driver-content
description: The CalcPrivateDepthStencilViewSize function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil view.
old-location: display\calcprivatedepthstencilviewsize.htm
old-project: display
ms.assetid: e5dfa018-f9a5-467f-8e84-9697d5f94689
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: display.calcprivatedepthstencilviewsize, CalcPrivateDepthStencilViewSize callback function [Display Devices], CalcPrivateDepthStencilViewSize, PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE, PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE, d3d10umddi/CalcPrivateDepthStencilViewSize, UserModeDisplayDriverDx10_Functions_514ed3bc-fc1d-4bda-bcc9-f90e6900c002.xml
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
-	CalcPrivateDepthStencilViewSize
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback function
The <b>CalcPrivateDepthStencilViewSize</b> function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a depth stencil view.

## Syntax

```
PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE Pfnd3d10ddiCalcprivatedepthstencilviewsize;

SIZE_T Pfnd3d10ddiCalcprivatedepthstencilviewsize(
   D3D10DDI_HDEVICE,
  CONST D3D10DDIARG_CREATEDEPTHSTENCILVIEW *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`




## Return Value

<b>CalcPrivateDepthStencilViewSize</b> returns the size of the memory region that the driver requires for creating a depth stencil view.

## Remarks

None.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddiarg_createdepthstencilview.md">D3D10DDIARG_CREATEDEPTHSTENCILVIEW</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D10DDI_CALCPRIVATEDEPTHSTENCILVIEWSIZE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>