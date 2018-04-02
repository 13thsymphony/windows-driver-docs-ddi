---
UID: NC:d3d10umddi.PFND3D10DDI_SETRASTERIZERSTATE
title: PFND3D10DDI_SETRASTERIZERSTATE
author: windows-driver-content
description: The SetRasterizerState function sets the rasterizer state.
old-location: display\setrasterizerstate.htm
old-project: display
ms.assetid: 8162c9c9-4ebd-45a9-adaf-576f25c3907e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3D10DDI_SETRASTERIZERSTATE, SetRasterizerState, SetRasterizerState callback function [Display Devices], UserModeDisplayDriverDx10_Functions_4f21a729-b192-441f-b80d-cae10432ab0a.xml, d3d10umddi/SetRasterizerState, display.setrasterizerstate
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
-	SetRasterizerState
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D10DDI_SETRASTERIZERSTATE callback function
The <i>SetRasterizerState</i> function sets the rasterizer state.

## Syntax

```
PFND3D10DDI_SETRASTERIZERSTATE Pfnd3d10ddiSetrasterizerstate;

void Pfnd3d10ddiSetrasterizerstate(
   D3D10DDI_HDEVICE,
   D3D10DDI_HRASTERIZERSTATE
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_HRASTERIZERSTATE`




## Return Value

None

The driver can use the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> callback function to set an error code. For more information about setting error codes, see the following Remarks section.

## Remarks

The driver should not encounter any error, except for D3DDDIERR_DEVICEREMOVED. Therefore, if the driver passes any error, except for D3DDDIERR_DEVICEREMOVED, in a call to the <a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a> function, the Microsoft Direct3D runtime will determine that the error is critical. Even if the device was removed, the driver is not required to return D3DDDIERR_DEVICEREMOVED; however, if device removal interfered with the operation of <i>SetRasterizerState</i> (which typically should not happen), the driver can return D3DDDIERR_DEVICEREMOVED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems.  |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff541833">D3D10DDI_DEVICEFUNCS</a>



<a href="https://msdn.microsoft.com/968b04a7-8869-410c-a6fc-83d57726858f">pfnSetErrorCb</a>