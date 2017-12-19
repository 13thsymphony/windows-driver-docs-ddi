---
UID: NC.d3d10umddi.PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
title: PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW
author: windows-driver-content
description: Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.
old-location: display\createvideodecoderoutputview.htm
old-project: display
ms.assetid: a5a32b4e-799c-4d18-995d-f804e6dff85c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: CreateVideoDecoderOutputView
req.alt-loc: D3d10umddi.h
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

# PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback



## -description
Creates a resource view for a video decoder. This view defines the output sample for the video decoding operation.



## -prototype

````
PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW CreateVideoDecoderOutputView;

HRESULT APIENTRY* CreateVideoDecoderOutputView(
  _In_       D3D10DDI_HDEVICE                           hDevice,
  _In_ const D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW *pCreateData,
  _In_       D3D11_1DDI_HVIDEODECODEROUTPUTVIEW         hView,
  _In_       D3D11_1DDI_HRTVIDEODECODEROUTPUTVIEW       hRTView
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device (graphics context).




### -param pCreateData [in]

A pointer to a <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddiarg_createvideodecoderoutputview.md">D3D11_1DDIARG_CREATEVIDEODECODEROUTPUTVIEW</a> structure. This structure specifies the attributes of the video decoder output view to be created.


### -param hView [in]

A handle to the driver's private data for the video decoder output view. For more information, see the Remarks section.


### -param hRTView [in]

A handle to the video decoder output view that the driver should use when it calls back into the Direct3D runtime.


## -returns
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

 


## -remarks
The Direct3D runtime calls <i>CreateVideoDecoderOutputView</i> after it has called the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_calcprivatevideoprocessoroutputviewsize.md">CalcPrivateVideoProcessorOutputViewSize</a>  to determine the size in bytes for the private data that the driver requires for the video decoder object. The runtime allocates the memory for this private data for the driver. The driver uses this memory to store private data that is related to the video decoder object.

When the runtime  calls <i>CreateVideoDecoderOutputView</i>, it passes the handle to the private data memory in the <i>hView</i> parameter. This handle is actually  a pointer to the memory. 


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>D3d10umddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
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
<a href="display.videodecoderbeginframe">VideoDecoderBeginFrame</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3D11_1DDI_CREATEVIDEODECODEROUTPUTVIEW callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

