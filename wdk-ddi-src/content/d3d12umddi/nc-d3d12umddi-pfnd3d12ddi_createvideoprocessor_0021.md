---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOPROCESSOR_0021
title: PFND3D12DDI_CREATEVIDEOPROCESSOR_0021
author: windows-driver-content
description: The pfnCreateVideoProcessor callback function creates a video processor.
old-location: display\pfnd3d12ddi_createvideoprocessor.htm
old-project: display
ms.assetid: 4F1AA75F-DDC7-490B-8CE2-590691991234
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
req.alt-api: pfnCreateVideoProcessor
req.alt-loc: D3d12umddi.h
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

# PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 callback



## -description
The <i>pfnCreateVideoProcessor</i> callback function creates a video processor.



## -prototype

````
PFND3D12DDI_CREATEVIDEOPROCESSOR_0021 pfnCreateVideoProcessor;

HRESULT  APIENTRY* pfnCreateVideoProcessor(
   D3D12DDI_HDEVICE         hDrvDevice,
   D3D12DDI_HVIDEOPROCESSOR hDrvVideoProcessor
)
{ ... }
````


## -parameters

### -param hDrvDevice 

The handle of a device driver.


### -param hDrvVideoProcessor 

The handle of a video processor.


## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks


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