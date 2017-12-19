---
UID: NS.D3D12UMDDI.D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
title: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
author: windows-driver-content
description: Create a video decoder heap.
old-location: display\d3d12ddiarg-create-video-decoder-heap-0033.htm
old-project: display
ms.assetid: 158411ee-6cc1-466d-b772-fe380b55baef
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033, D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
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
req.alt-api: D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033
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

# D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 structure



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

Create a video decoder heap.



## -syntax

````
typedef struct _D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033 {
  UINT                                      NodeMask;
  D3D12DDI_VIDEO_DECODE_CONFIGURATION_0020  Configuration;
  UINT                                      DecodeWidth;
  UINT                                      DecodeHeight;
  DXGI_FORMAT                               Format;
  DXGI_RATIONAL                             FrameRate;
  UINT                                      BitRate;
  UINT                                      MaxDecodePictureBufferCount;
} D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033, D3D12DDIARG_CREATE_VIDEO_DECODER_HEAP_0033;
````


## -struct-fields

### -field NodeMask

The set of nodes.


### -field Configuration

The video decode configuration.


### -field DecodeWidth

Decode width.


### -field DecodeHeight

Decode height.


### -field Format

The resource data format.


### -field FrameRate

A rational number that specifies the frame rate.


### -field BitRate

The number of bits per second.


### -field MaxDecodePictureBufferCount

Maximum decode picture buffer count.


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