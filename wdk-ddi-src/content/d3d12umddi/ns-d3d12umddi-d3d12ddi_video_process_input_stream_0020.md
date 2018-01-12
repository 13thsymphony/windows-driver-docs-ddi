---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
title: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
author: windows-driver-content
description: Contains stream information for the video processor blend functionality.
old-location: display\d3d12ddi_video_process_input_stream.htm
old-project: display
ms.assetid: DB0AF7A5-8E90-45B8-AF9C-58BFF7CE066E
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020, D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
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
req.typenames: D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020
---

# D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 structure



## -description
Contains stream information for the video processor blend functionality.



## -syntax

````
typedef struct D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020 {
  D3D12DDI_HRESOURCE                          hDrvInputTexture;
  UINT                                        Subresource;
  D3D12DDI_VIDEO_PROCESS_REFERENCES_INFO_0020 ReferenceInfo;
} D3D12DDI_VIDEO_PROCESS_INPUT_STREAM_0020;
````


## -struct-fields

### -field hDrvInputTexture

The current input field or frame.  


### -field Subresource

The subresource index to use of the <i>hDrvInputTexture</i> argument.


### -field ReferenceInfo

The set of references to be able to perform processing.  


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d12umddi.h (include D3d12umddi.h)</dt>
</dl>
</td>
</tr>
</table>