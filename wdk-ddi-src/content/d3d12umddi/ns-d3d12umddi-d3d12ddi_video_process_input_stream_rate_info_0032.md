---
UID: NS.D3D12UMDDI.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
author: windows-driver-content
description: The video process input stream rate info.
old-location: display\d3d12ddi-video-process-input-stream-rate-info-0032.htm
old-project: display
ms.assetid: 4ca68dac-ead1-431e-a97e-af99ef966417
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032
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
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 structure



## -description
The video process input stream rate info.


## -syntax

````
typedef struct _D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032 {
  UINT  OutputIndex;
  UINT  InputFrameOrField;
} D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_RATE_INFO_0032;
````


## -struct-fields

### -field OutputIndex

The output index.

### -field InputFrameOrField

The input frame or field.

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