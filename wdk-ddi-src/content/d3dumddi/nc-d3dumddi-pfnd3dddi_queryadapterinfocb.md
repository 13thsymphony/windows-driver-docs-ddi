---
UID : NC:d3dumddi.PFND3DDDI_QUERYADAPTERINFOCB
title : PFND3DDDI_QUERYADAPTERINFOCB
author : windows-driver-content
description : The pfnQueryAdapterInfoCb function retrieves graphics adapter information.
old-location : display\pfnqueryadapterinfocb.htm
old-project : display
ms.assetid : 8008574f-a89e-4fed-b745-7cf5baa68e64
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.pfnqueryadapterinfocb, pfnQueryAdapterInfoCb callback function [Display Devices], pfnQueryAdapterInfoCb, PFND3DDDI_QUERYADAPTERINFOCB, PFND3DDDI_QUERYADAPTERINFOCB, d3dumddi/pfnQueryAdapterInfoCb, D3Druntime_Functions_ca5c02c9-ad59-4a10-8cb7-92d815cd6856.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3dumddi.h
req.include-header : D3dumddi.h
req.target-type : Desktop
req.target-min-winverclnt : Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr : 
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
req.typenames : DXGK_PTE
---


# PFND3DDDI_QUERYADAPTERINFOCB callback function
The <b>pfnQueryAdapterInfoCb</b> function retrieves graphics adapter information.

## Syntax

```
PFND3DDDI_QUERYADAPTERINFOCB Pfnd3dddiQueryadapterinfocb;

HRESULT Pfnd3dddiQueryadapterinfocb(
  HANDLE hAdapter,
  CONST D3DDDICB_QUERYADAPTERINFO *
)
{...}
```

## Parameters

`hAdapter`

A handle to the graphics adapter object.

`*`




## Return Value

<b>pfnQueryAdapterInfoCb</b> returns one of the following values:
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
Information was successfully retrieved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_INVALIDARG</b></dt>
</dl>
</td>
<td width="60%">
Parameters were validated and determined to be incorrect.

</td>
</tr>
</table> 

This function might also return other HRESULT values.

## Remarks

Before the Microsoft Direct3D runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a> or <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a> function to create the graphics context, the user-mode display driver should call <b>pfnQueryAdapterInfoCb</b> to retrieve information about the graphics hardware. This order is especially important for a multiple-monitor system. 

In the <b>pfnQueryAdapterInfoCb</b> call, the user-mode display driver sends a buffer that the display miniport driver fills with configuration data. After receiving this configuration data, the user-mode display driver can accurately report its capabilities when the runtime calls the user-mode display driver's <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a> and GetCaps(D3D10_2) functions. When the runtime subsequently calls other user-mode display driver functions that are specified in the <a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>, <a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>, or <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a> structure, the user-mode display driver can generate command streams that the hardware can process.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating systems. Available in Windows Vista and later versions of the Windows operating systems. |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_devicefuncs.md">D3D11DDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d10ddi_devicefuncs.md">D3D10DDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_devicefuncs.md">D3DDDI_DEVICEFUNCS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddi_adaptercallbacks.md">D3DDDI_ADAPTERCALLBACKS</a>

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_queryadapterinfo.md">D3DDDICB_QUERYADAPTERINFO</a>

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi_createdevice.md">CreateDevice(D3D10)</a>

<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_createdevice.md">CreateDevice</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_QUERYADAPTERINFOCB callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>