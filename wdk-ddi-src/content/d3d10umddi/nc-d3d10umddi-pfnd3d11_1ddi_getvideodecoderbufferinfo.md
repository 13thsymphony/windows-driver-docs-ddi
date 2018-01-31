---
UID : NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO
title : PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO
author : windows-driver-content
description : Queries the description of a video decoder buffer for a specified video operation.
old-location : display\getvideodecoderbufferinfo.htm
old-project : display
ms.assetid : f129ae04-da7f-4681-a266-ac13317a895d
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.getvideodecoderbufferinfo, pfnGetVideoDecoderBufferInfo callback function [Display Devices], pfnGetVideoDecoderBufferInfo, PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO, PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO, d3d10umddi/pfnGetVideoDecoderBufferInfo
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : d3d10umddi.h
req.include-header : D3d10umddi.h
req.target-type : Desktop
req.target-min-winverclnt : Windows 8
req.target-min-winversvr : Windows Server 2012
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
req.typenames : SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO callback function
Queries the description of a video decoder buffer for a specified video operation.

## Syntax

```
PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO Pfnd3d111DdiGetvideodecoderbufferinfo;

void Pfnd3d111DdiGetvideodecoderbufferinfo(
   D3D10DDI_HDEVICE,
  CONST D3D11_1DDI_VIDEO_DECODER_DESC *,
   UINT,
  D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`



`UINT`



`*`




## Return Value

This callback function does not return a value.

## Remarks

The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i>  and <i>Index</i> parameter data is valid before it calls the <b>GetVideoDecoderBufferInfo</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_getvideodecoderbuffertypecount.md">GetVideoDecoderBufferTypeCount</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_buffer_info.md">D3D11_1DDI_VIDEO_DECODER_BUFFER_INFO</a>

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETVIDEODECODERBUFFERINFO callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>