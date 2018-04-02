---
UID: NC:d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODER
title: PFND3D11_1DDI_CREATEVIDEODECODER
author: windows-driver-content
description: Creates a video decoder object.
old-location: display\createvideodecoder.htm
old-project: display
ms.assetid: 41254f99-1806-428c-8bf3-7e736dbeec84
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: CreateVideoDecoder, CreateVideoDecoder callback function [Display Devices], PFND3D11_1DDI_CREATEVIDEODECODER, d3d10umddi/CreateVideoDecoder, display.createvideodecoder
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
-	CreateVideoDecoder
product:
- Windows
targetos: Windows
req.typenames: SETRESULT_INFO, *PSETRESULT_INFO
---


# PFND3D11_1DDI_CREATEVIDEODECODER callback function
Creates a video decoder object.

## Syntax

```
PFND3D11_1DDI_CREATEVIDEODECODER Pfnd3d111DdiCreatevideodecoder;

HRESULT Pfnd3d111DdiCreatevideodecoder(
   D3D10DDI_HDEVICE,
  CONST D3D11_1DDIARG_CREATEVIDEODECODER *,
   D3D11_1DDI_HDECODE,
   D3D11_1DDI_HRTDECODE
)
{...}
```

## Parameters

`D3D10DDI_HDEVICE`



`*`



`D3D11_1DDI_HDECODE`



`D3D11_1DDI_HRTDECODE`




## Return Value

<b>CreateVideoDecoder</b> returns one of the following values:

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
The video decoder object was created successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>D3DDDIERR_DEVICEREMOVED</b></dt>
</dl>
</td>
<td width="60%">
The graphics adapter was removed.

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

The Microsoft Direct3D runtime calls <i>CreateVideoDecoder</i> after it has called the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh451610">CalcPrivateVideoDecoderSize</a> to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoder</i>, it passes the handle to the private data memory in the <i>hDecoder</i> parameter. This handle is actually a pointer to the memory. 

The driver must keep track of the handle to the display device that was used to create the cryptographic session. The driver should fail all subsequent calls that use this created cryptographic session, such as <a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>, if the display device that is specified in those calls is different from the display device that was used to create the video decoder.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows Server 2012 |
| **Target Platform** | Desktop |
| **Header** | d3d10umddi.h (include D3d10umddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh451610">CalcPrivateVideoDecoderSize</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh406310">D3D11_1DDIARG_CREATEVIDEODECODER</a>



<a href="https://msdn.microsoft.com/a48dcbae-3236-4523-bc14-4be694da9a7b">NegotiateCryptoSessionKeyExchange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451697">VideoDecoderBeginFrame</a>