---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1
title: PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1
author: windows-driver-content
description: VideoDecoderSubmitBuffers1 submits one or more buffers for decoding.
old-location: display\videodecodersubmitbuffers1.htm
old-project: display
ms.assetid: 708A7F64-F8A8-4D0B-A824-CC8DD158216A
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1, d3d10umddi/pfnVideoDecoderSubmitBuffers1, display.videodecodersubmitbuffers1, pfnVideoDecoderSubmitBuffers1, pfnVideoDecoderSubmitBuffers1 callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	D3d10umddi.h
api_name:
-	pfnVideoDecoderSubmitBuffers1
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1 callback function
<b>VideoDecoderSubmitBuffers1</b> submits one or more buffers for decoding.

## Syntax

```
PFND3DWDDM2_0DDI_VIDEODECODERSUBMITBUFFERS1 Pfnd3dwddm20DdiVideodecodersubmitbuffers1;

HRESULT Pfnd3dwddm20DdiVideodecodersubmitbuffers1(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HDECODE hDecode,
  UINT BufferCount,
  CONST D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1 *pBufferDesc
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

`hDecode`

A handle to the video decoder object that was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a>DDI.

`BufferCount`

The number of buffers in the array that is referenced by the <b>pBufferDesc</b> member.

`*pBufferDesc`

A pointer to an array of one or more <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_buffer_desc1.md">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a> structures.


## Return Value

Returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
Private driver data was successfully returned.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
</td>
<td width="60%">

        Memory was not available to complete the operation.


</td>
</tr>
</table>

## Remarks

The <b>pBufferDesc</b> member points to an array of one or more <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_buffer_desc1.md">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a> structures. Each element in the array describes a compressed video frame buffer that is submitted for decoding.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_decoder_buffer_desc1.md">D3DWDDM2_0DDI_VIDEO_DECODER_BUFFER_DESC1</a>