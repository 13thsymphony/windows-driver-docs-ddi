---
UID : NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
title : PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
author : windows-driver-content
description : Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.
old-location : display\createvideodecoderoutputview.htm
old-project : display
ms.assetid : a5a32b4e-799c-4d18-995d-f804e6dff85c
ms.author : windowsdriverdev
ms.date : 12/29/2017
ms.keywords : _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api : CreateVideoDecoderOutputView
req.alt-loc : D3d10umddi.h
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
req.typenames : "*PSETRESULT_INFO, SETRESULT_INFO"
---


# PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback function
Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.

## Syntax

```
PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW Pfnd3d111DdiCreatevideodecoderoutputview;

HRESULT Pfnd3d111DdiCreatevideodecoderoutputview(
   D3D10DDI_HDEVICE,
  CONST D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW *,
   D3D11_1DDI_HVIDEODECODEROUTPUTVIEW,
   D3D11_1DDI_HRTVIDEODECODEROUTPUTVIEW
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`



`D3D11_1DDI_HVIDEODECODEROUTPUTVIEW`



`D3D11_1DDI_HRTVIDEODECODEROUTPUTVIEW`




## Return Value

<b>CreateVideoDecoderOutputView</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The video decoder output view was created successfully.
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>The graphics adapter was removed.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

## Remarks

The Direct3D runtime calls <i>CreateVideoDecoderOutputView</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md">CalcPrivateVideoProcessorOutputViewSize</a>  to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoderOutputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually  a pointer to the memory.

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

<dl>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md">CalcPrivateVideoProcessorOutputViewSize</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_negotiatecryptosessionkeyeschange.md">NegotiateCryptoSessionKeyExchange</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoder.md">D3D11_1DDIARG_CREATEVIDEODECODER</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderbeginframe.md">VideoDecoderBeginFrame</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>