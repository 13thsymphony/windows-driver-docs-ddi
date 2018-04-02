---
UID: NC:d3dumddi.PFND3DDDI_PRESENT1
title: PFND3DDDI_PRESENT1
author: windows-driver-content
description: Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.
old-location: display\pfnpresent1_d3d_.htm
old-project: display
ms.assetid: 8BB8E85F-B081-422E-ACE1-C2312BA28B9F
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: PFND3DDDI_PRESENT1, d3dumddi/pfnPresent1, display.pfnpresent1_d3d_, pfnPresent1, pfnPresent1 callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
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
-	D3dumddi.h
api_name:
-	pfnPresent1
product:
- Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_PRESENT1 callback function
Notifies the user-mode display driver that an application finished rendering and that all ownership of the shared resource is released, and requests that the driver display to the destination surface.

## Syntax

```
PFND3DDDI_PRESENT1 Pfnd3dddiPresent1;

HRESULT Pfnd3dddiPresent1(
  HANDLE hDevice,
  D3DDDIARG_PRESENT1 *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

Returns <b>S_OK</b> or an appropriate error result if the function does not complete successfully.

## Remarks

The user-mode display driver must submit all partially built render data (command buffers) by calling the <a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>  function. The driver must make only  a single call to <b>pfnRenderCb</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8.1,WDDM 1.3 and later Windows Server 2012 R2 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn457997">D3DDDIARG_PRESENT1</a>



<a href="https://msdn.microsoft.com/f242162e-6237-469c-b178-5a51dcf69e32">pfnRenderCb</a>