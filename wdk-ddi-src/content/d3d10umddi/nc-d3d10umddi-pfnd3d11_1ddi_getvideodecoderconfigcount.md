---
UID : NC:d3d10umddi.PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT
title : PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT
author : windows-driver-content
description : Queries the number of video decoder configurations that are supported by the display miniport driver for the specified decoder operation.
old-location : display\getvideodecoderconfigcount.htm
old-project : display
ms.assetid : 5b4cc185-8579-4c13-932f-23065697c4ee
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : display.getvideodecoderconfigcount, pfnGetVideoDecoderConfigCount callback function [Display Devices], pfnGetVideoDecoderConfigCount, PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT, PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT, d3d10umddi/pfnGetVideoDecoderConfigCount
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
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT callback function
Queries the number of video decoder configurations that are supported by the display miniport driver for the specified decoder operation.

## Syntax

```
PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT Pfnd3d111DdiGetvideodecoderconfigcount;

void Pfnd3d111DdiGetvideodecoderconfigcount(
   D3D10DDI_HDEVICE,
  CONST D3D11_1DDI_VIDEO_DECODER_DESC *,
  UINT *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`



`*`




## Return Value

This callback function does not return a value.

## Remarks

The Microsoft Direct3D runtime verifies that the <i>pDecodeDesc</i>  parameter data is valid before it calls the <b>GetVideoDecoderConfigCount</b> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_GETVIDEODECODERCONFIGCOUNT callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>