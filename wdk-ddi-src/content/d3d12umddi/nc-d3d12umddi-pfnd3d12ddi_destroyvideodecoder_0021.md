---
UID: NC.d3d12umddi.PFND3D12DDI_DESTROYVIDEODECODER_0021
title: PFND3D12DDI_DESTROYVIDEODECODER_0021
author: windows-driver-content
description: Destroys the video decoder.
old-location: display\pfnd3d12ddi_destroyvideodecoder_.htm
old-project: display
ms.assetid: 97028FEB-A3C2-4C2F-B64E-07024BC3C382
ms.author: windowsdriverdev
ms.date: 12/6/2017
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
req.alt-api: PFND3D12DDI_DESTROYVIDEODECODER_0021
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
---

# PFND3D12DDI_DESTROYVIDEODECODER_0021 callback



## -description
Destroys the video decoder.


## -prototype

````
VOID APIENTRY PFND3D12DDI_DESTROYVIDEODECODER_0021(
   D3D12DDI_HDEVICE       D3d12ddi_hdevice,
   D3D12DDI_HVIDEODECODER D3d12ddi_hvideodecoder
);
````


## -parameters

### -param D3d12ddi_hdevice 

Holds the HDevice.

### -param D3d12ddi_hvideodecoder 

Holds the HVideoDecoder

## -returns
This callback function does not return a value.

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