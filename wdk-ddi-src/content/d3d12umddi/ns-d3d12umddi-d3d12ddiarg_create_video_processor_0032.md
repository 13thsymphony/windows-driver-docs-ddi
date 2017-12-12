---
UID: NS.D3D12UMDDI.D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
title: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
author: windows-driver-content
description: Creates a video processor.
old-location: display\d3d12ddiarg-create-video-processor-0032.htm
old-project: display
ms.assetid: 6b945476-c1cf-4bf8-8273-bb3d05b90277
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
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
req.alt-api: D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032
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

# D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 structure



## -description
Creates a video processor.



## -syntax

````
typedef struct _D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032 {
  UINT                                               NodeMask;
  D3D12DDI_VIDEO_PROCESS_OUTPUT_STREAM_DESC_0032     OutputStream;
  D3D12DDI_VIDEO_PROCESSOR_INPUT_STREAM_DESC_0032 *  pInputStreams;
  UINT                                               NumInputStreams;
} D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032, D3D12DDIARG_CREATE_VIDEO_PROCESSOR_0032;
````


## -struct-fields

### -field NodeMask

Represents the set of nodes.


### -field OutputStream

The output stream.


### -field pInputStreams

The input stream.


### -field NumInputStreams

The number of input streams.


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