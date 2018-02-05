---
UID : NE:d3d12umddi.D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020
title : D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020
author : windows-driver-content
description : Contains video decode support flags.
old-location : display\d3d12ddi_video_decode_support_flags.htm
old-project : display
ms.assetid : 3AF74BA9-168C-4EB0-B219-CC6BA58E1BCD
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_NONE, D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_SUPPORTED, d3d12umddi/D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_NONE, display.d3d12ddi_video_decode_support_flags, D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020, d3d12umddi/D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020, D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020 enumeration [Display Devices]
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : enum
req.header : d3d12umddi.h
req.include-header : D3d12umddi.h
req.target-type : Windows
req.target-min-winverclnt : 
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
req.typenames : D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020
---

# D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020 Enumeration
Contains video decode support flags.

## Syntax
````
typedef enum D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020 { 
  D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_NONE       = 0,
  D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_SUPPORTED  = 0x1
} D3D12DDI_VIDEO_DECODE_SUPPORT_FLAGS_0020;
````

## Constants

<table>

<tr>
<td>D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_NONE</td>
<td>No Flags set.</td>
</tr>

<tr>
<td>D3D12DDI_VIDEO_DECODE_SUPPORT_FLAG_0020_SUPPORTED</td>
<td>Indicates if real-time decoding is supported with the specified input data.  The presence of this flag is a hint that the decoder is capable of decoding the compressed bitstream fast enough to support realtime decoding.  The absence of this flag indicates that the decoder with the specified input parameters is only appropriate for non-realtime scenarios like transcoding.</td>
</tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | d3d12umddi.h (include D3d12umddi.h) |