---
UID: NC:d3d10umddi.PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW
title: PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW
author: windows-driver-content
description: Releases resources for the video processor input view that were created through a call to the CreateVideoProcessorInputView function.
old-location: display\destroyvideoprocessorinputview.htm
old-project: display
ms.assetid: 3a815201-091b-4c85-a62a-2cdbbaf0bf95
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: pfnDestroyVideoProcessorInputView
req.alt-loc: D3d10umddi.h
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW callback



## -description
Releases resources for the video processor input view that were created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md">CreateVideoProcessorInputView</a> function.




## -prototype

````
PFND3D11_1DDI_DESTROYVIDEOPROCESSORINPUTVIEW pfnDestroyVideoProcessorInputView;

VOID APIENTRY* pfnDestroyVideoProcessorInputView(
  _In_ D3D10DDI_HDEVICE                    hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSORINPUTVIEW hView
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param hView [in]

A handle to the driver's private data for the video processor input view. This handle was created by the Direct3D runtime and passed to the driver in the call to <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideoprocessorinputview.md">CreateVideoProcessorInputView</a>.


## -returns
This callback function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>