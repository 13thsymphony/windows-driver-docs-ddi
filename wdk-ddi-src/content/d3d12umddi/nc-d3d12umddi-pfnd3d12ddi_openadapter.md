---
UID: NC:d3d12umddi.PFND3D12DDI_OPENADAPTER
title: PFND3D12DDI_OPENADAPTER
author: windows-driver-content
description: The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls.
old-location: display\pfnd3d12ddi_openadapter.htm
old-project: display
ms.assetid: FEDC2FB5-9F1A-4829-A98D-3BEA4218AE3D
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3D11_1DDI_GETCAPTUREHANDLEDATA, D3D11_1DDI_GETCAPTUREHANDLEDATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFND3D12DDI_OPENADAPTER
req.alt-loc: d3d12umddi.h
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
req.typenames: D3D11_1DDI_GETCAPTUREHANDLEDATA
---

# PFND3D12DDI_OPENADAPTER callback



## -description
The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls. 



## -prototype

````
HRESULT APIENTRY PFND3D12DDI_OPENADAPTER(
  _Inout_ D3D12DDIARG_OPENADAPTER *pOpenData
);
````


## -parameters

### -param pOpenData [in, out]

A pointer to a <a href="..\d3d12umddi\ns-d3d12umddi-d3d12ddiarg_openadapter.md">D3D12DDIARG_OPENADAPTER</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.


## -returns

             PFND3D12DDI_OPENADAPTER returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The graphics adapter object was successfully created.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
                PFND3D12DDI_OPENADAPTER could not allocate memory that was required for it to complete.

 


## -remarks
The graphics adapter object that is created by the PFND3D12DDI_OPENADAPTER function represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling <a href="https://msdn.microsoft.com/library/windows/hardware/mt779070">PFND3D12DDI_CREATEDEVICE_0003</a>, the user-mode display driver should call the <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_queryadapterinfocb.md">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h</dt>
</dl>
</td>
</tr>
</table>