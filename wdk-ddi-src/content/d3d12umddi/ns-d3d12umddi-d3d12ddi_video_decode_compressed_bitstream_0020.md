---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
title: D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
author: windows-driver-content
description: Contains the compressed bitstream from which to decode.
old-location: display\d3d12ddi_video_decode_compressed_bitstream.htm
old-project: display
ms.assetid: 24A1D8C7-E432-45CB-8DEA-C1137159E319
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020, D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
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
req.alt-api: D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
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
req.typenames: D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020
---

# D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020 structure



## -description
Contains the compressed bitstream from which  to decode.



## -syntax

````
typedef struct D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020 {
  D3D12DDI_HRESOURCE hDrvBuffer;
  UINT64             Offset;
} D3D12DDI_VIDEO_DECODE_COMPRESSED_BITSTREAM_0020;
````


## -struct-fields

### -field hDrvBuffer

The source buffer that contains the compressed bitstream to decode.


### -field Offset

The offset to the beginning of the first slice.  This offset has alignment requirements based on the tier value.


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