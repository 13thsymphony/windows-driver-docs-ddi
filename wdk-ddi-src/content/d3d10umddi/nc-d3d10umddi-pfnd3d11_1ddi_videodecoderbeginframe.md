---
UID : NC:d3d10umddi.PFND3D11_1DDI_VIDEODECODERBEGINFRAME
title : PFND3D11_1DDI_VIDEODECODERBEGINFRAME
author : windows-driver-content
description : Starts a DirectX Video Acceleration (DXVA) decoding operation to decode a video frame.
old-location : display\videodecoderbeginframe.htm
old-project : display
ms.assetid : 5aebc8c9-baa1-457f-9e46-3a86929ba0b5
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
req.alt-api : pfnVideoDecoderBeginFrame
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


# PFND3D11_1DDI_VIDEODECODERBEGINFRAME callback function
Starts a DirectX Video Acceleration (DXVA) decoding operation to decode a video frame.

## Syntax

```
PFND3D11_1DDI_VIDEODECODERBEGINFRAME Pfnd3d111DdiVideodecoderbeginframe;

HRESULT Pfnd3d111DdiVideodecoderbeginframe(
   D3D10DDI_HDEVICE,
   D3D11_1DDI_HDECODE,
  CONST D3D11_1DDIARG_VIDEODECODERBEGINFRAME *
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`D3D11_1DDI_HDECODE`



`*`




## Return Value

<b>VideoDecoderBeginFrame</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The decoding operation was started successfully.
<dl>
<dt><b>E_OUTOFMEMORY</b></dt>
</dl>
        Memory was not available to complete the operation.

## Remarks

If the <b>VideoDecoderBeginFrame</b> returns <b>S_OK</b>, the Microsoft Direct3D runtime calls the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecodersubmitbuffers.md">VideoDecoderSubmitBuffers</a> function  to perform the decoding operations. When all decoding operations have been executed, the runtime calls the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderendframe.md">VideoDecoderEndFrame</a> function to stop the decoding operation on a video frame.



The <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_videodecoderbeginframe.md">D3D11_1DDIARG_VIDEODECODERBEGINFRAME</a> structure contains the following data:

The resource that will receive the decrypted and decoded data.

A content key that was used to encrypt the video frame data. 

If the <b>pContentKey</b> member of this structure is not set to NULL, the buffer that is referenced by this member contains a per-frame content key. This key must be used to decrypt the data instead of using the session key.

If the <b>pContentKey</b> member is set to NULL, the video frame data should be decrypted by using the session key.

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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_createvideodecoder.md">CreateVideoDecoder</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecoderendframe.md">VideoDecoderEndFrame</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videodecodersubmitbuffers.md">VideoDecoderSubmitBuffers</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_VIDEODECODERBEGINFRAME callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>