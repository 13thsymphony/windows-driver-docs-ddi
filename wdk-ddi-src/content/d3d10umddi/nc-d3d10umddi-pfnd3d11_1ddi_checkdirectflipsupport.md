---
UID : NC:d3d10umddi.PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT
title : PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT
author : windows-driver-content
description : Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.
old-location : display\checkdirectflipsupport_d3d11_1_.htm
old-project : display
ms.assetid : 2acf84cb-5e51-4aa8-96ce-96abc6ceec8c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.checkdirectflipsupport_d3d11_1_, CheckDirectFlipSupport(D3D11_1) callback function [Display Devices], CheckDirectFlipSupport(D3D11_1), PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT, PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT, d3d10umddi/CheckDirectFlipSupport(D3D11_1), display.pfncheckdirectflipsupport
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
req.typenames : SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT callback function
Called by the Desktop Window Manager (DWM) to verify that the user-mode driver supports Direct Flip operations, in which video memory is seamlessly flipped between an application's managed primary allocations and the DWM's managed primary allocations.

## Syntax

```
PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT Pfnd3d111DdiCheckdirectflipsupport;

void Pfnd3d111DdiCheckdirectflipsupport(
   D3D10DDI_HDEVICE,
   D3D10DDI_HRESOURCE,
   D3D10DDI_HRESOURCE,
  UINT CheckDirectFlipFlags,
  BOOL *pSupported
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D10DDI_HRESOURCE`



`D3D10DDI_HRESOURCE`



`CheckDirectFlipFlags`

If this parameter has a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>, seamless flipping should occur immediately and does not have to be synchronized with a VSync interrupt.

`*pSupported`




## Return Value

This callback function does not return a value.

## Remarks

This function is called at least once before the DWM attempts to present to a Direct Flip swapchain. It is also called after each mode change occurs, or after the DWM re-creates its own swapchain for any reason.

The user-mode driver should ensure that the managed primary allocations of the application and the DWM have the following compatible resources:
<ul>
<li>Stereo resources.</li>
<li>Multiple Sample Anti Aliasing (MSAA) formats.</li>
<li>Swizzle formats. If the swizzle can only be changed at every VSync interval, ensure that the <i>CheckDirectFlipFlags</i> parameter does not have a value of <b>D3D11_1DDI_CHECK_DIRECT_FLIP_IMMEDIATE</b>.</li>
<li>Both managed primary allocations should be created using the same <b>VidPnSourceId</b> value in the <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a> structure.</li>
<li>Display adapter configurations are linked.</li>
</ul>The user-mode driver might need to call the kernel-mode driver to perform these validations. To do this, call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a> callback function and then call the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a> function to access the kernel-mode driver's resource allocation data.

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

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_allocationinfo.md">D3DDDI_ALLOCATIONINFO</a>

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_gethandledata.md">DxgkCbGetHandleData</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_escapecb.md">pfnEscapeCb</a>

<a href="..\d3d10umddi\ne-d3d10umddi-d3d11_1_ddi_check_direct_flip_flags.md">D3D11_1_DDI_CHECK_DIRECT_FLIP_FLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CHECKDIRECTFLIPSUPPORT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>