---
UID: NC:d3dumddi.PFND3DDDI_CHECKDIRECTFLIPSUPPORT
title: PFND3DDDI_CHECKDIRECTFLIPSUPPORT
author: windows-driver-content
description: Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.
old-location: display\checkdirectflipsupport.htm
old-project: display
ms.assetid: BB909041-0194-4828-ACA2-E3F6B1974DBB
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CheckDirectFlipSupport, CheckDirectFlipSupport callback function [Display Devices], PFND3DDDI_CHECKDIRECTFLIPSUPPORT, d3dumddi/CheckDirectFlipSupport, display.checkdirectflipsupport
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	d3dumddi.h
api_name:
-	CheckDirectFlipSupport
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_CHECKDIRECTFLIPSUPPORT callback function
Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.

## Syntax

```
PFND3DDDI_CHECKDIRECTFLIPSUPPORT Pfnd3dddiCheckdirectflipsupport;

HRESULT Pfnd3dddiCheckdirectflipsupport(
  HANDLE hDevice,
  D3DDDIARG_CHECKDIRECTFLIPSUPPORT *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context).

`*`




## Return Value

Returns S_OK or an appropriate error result if the operation is not successfully performed.

## Remarks

This function is called at least once before the DWM attempts to present to a Direct Flip swapchain. It is also called after each mode change occurs, or after the DWM re-creates its own swapchain for any reason.

The user-mode driver should ensure that the managed primary allocations of the application and the DWM have the following compatible resources:

<ul>
<li>Stereo resources.</li>
<li>Multiple Sample Anti Aliasing (MSAA) formats.</li>
<li>Swizzle formats. If the swizzle can only be changed at every VSync interval, ensure that the <i>CheckDirectFlipFlags</i> member of the <a href="..\d3dumddi\ne-d3dumddi-d3dddi_check_direct_flip_flags.md">D3DDDI_CHECK_DIRECT_FLIP_FLAGS</a> structure does not have a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>.</li>
<li>Both managed primary allocations should be created using the same <b>VidPnSourceId</b> value in the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structure.</li>
<li>Display adapter configurations are linked.</li>
</ul>
The user-mode driver might need to call the kernel-mode driver to perform these validations. To do this, call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a> callback function and then call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a> function to access the kernel-mode driver's resource allocation data.

Because the DWM typically creates its own device using the highest possible Microsoft Direct3D feature level, the DWM will not call this function if the hardware supports a Direct3D device driver interface (DDI) that is greater than version 9.3. However, any Microsoft Direct3D 9 driver should implement this function to enable the Direct Flip user experience.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>



<a href="..\d3dumddi\ne-d3dumddi-d3dddi_check_direct_flip_flags.md">D3DDDI_CHECK_DIRECT_FLIP_FLAGS</a>