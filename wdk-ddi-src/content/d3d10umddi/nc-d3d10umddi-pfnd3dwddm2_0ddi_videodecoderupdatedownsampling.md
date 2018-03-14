---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING
title: PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING
author: windows-driver-content
description: Updates the decoder down sampling parameters. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videodecoderupdatedownsampling.htm
old-project: display
ms.assetid: DBF0F62D-E6E5-4711-9A7A-19C88F62575D
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING, d3d10umddi/pfnVideoDecoderUpdateDownsampling, display.videodecoderupdatedownsampling, pfnVideoDecoderUpdateDownsampling, pfnVideoDecoderUpdateDownsampling callback function [Display Devices]
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
-	pfnVideoDecoderUpdateDownsampling
product: Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING callback function
Updates the decoder down sampling parameters. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.

## Syntax

```
PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING Pfnd3dwddm20DdiVideodecoderupdatedownsampling;

HRESULT Pfnd3dwddm20DdiVideodecoderupdatedownsampling(
  D3D10DDI_HDEVICE hDevice,
  D3D11_1DDI_HDECODE hDecoder,
  CONST D3D11_1DDI_VIDEO_DECODER_DESC *pOutputDesc,
  D3DDDI_COLOR_SPACE_TYPE OutputColorSpace
)
{...}
```

## Parameters

`hDevice`

A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.

`hDecoder`

A handle to the video decoder object.

`*pOutputDesc`

Contains the resolution and the format of the output/display frames.  This is the destination resolution and format of the down sample operation.



<div class="alert"><b>Note</b>  The decode profile member (<b>Guid</b>) of <b>pOutputDesc</b> can be ignored.</div>
<div> </div>

`OutputColorSpace`

A <a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a> value that contains the color space information of the output/display frame data.


## Return Value

If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.

## Remarks

This function can only be called after <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling.md">VideoDecoderEnableDownsampling</a> has been called.



This function will only be called if the driver reports the <b>D3DWDDM2_0DDI_VIDEO_DECODER_CAPS_DOWN_SAMPLE_DYNAMIC</b> capability.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>



<a href="..\d3dukmdt\ne-d3dukmdt-d3dddi_color_space_type.md">D3DDDI_COLOR_SPACE_TYPE</a>



<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_decoder_desc.md">D3D11_1DDI_VIDEO_DECODER_DESC</a>



<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3dwddm2_0ddi_videodecoderenabledownsampling.md">VideoDecoderEnableDownsampling</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_VIDEODECODERUPDATEDOWNSAMPLING callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>