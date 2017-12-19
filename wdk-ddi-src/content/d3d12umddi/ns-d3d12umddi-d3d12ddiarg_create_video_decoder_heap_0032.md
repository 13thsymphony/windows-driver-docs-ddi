---
UID: NS.D3D12UMDDI.D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
title: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
author: windows-driver-content
description: Creates a video decoder heap.
old-location: display\d3d12ddiarg-create-video-decoder-heap-0032.htm
old-project: display
ms.assetid: 86f8021d-9b02-457f-9bee-4631c711094f
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032, D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
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
req.alt-api: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032
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

# D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 structure



## -description
Creates a video decoder heap.



## -syntax

````
typedef struct _D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032 {
  UINT                                      NodeMask;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020  Configuration;
  UINT                                      DecodeWidth;
  UINT                                      DecodeHeight;
  UINT                                      MaxDecodePictureBufferCount;
  DXGI_RATIONAL                             FrameRate;
  UINT                                      BitRate;
} D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032, D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0032;
````


## -struct-fields

### -field NodeMask

Represents the set of nodes.


### -field Configuration

The video decode configuration.


### -field DecodeWidth

The decode width.


### -field DecodeHeight

The decode height.


### -field MaxDecodePictureBufferCount

The max decode picture buffer count.


### -field FrameRate

The frame rate.


### -field BitRate

The bitrate.


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