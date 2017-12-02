---
UID: NS.d3d10umddi.D3D11_1DDIARG_VIDEODECODERBEGINFRAME
title: D3D11_1DDIARG_VIDEODECODERBEGINFRAME
author: windows-driver-content
description: Specifies a content key in a call to the VideoDecoderBeginFrame function.
old-location: display\d3d11_1ddiarg_videodecoderbeginframe.htm
old-project: display
ms.assetid: e2664aec-dc96-4cf6-921b-ccd4ee6cf04e
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D11_1DDIARG_VIDEODECODERBEGINFRAME, D3D11_1DDIARG_VIDEODECODERBEGINFRAME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11_1DDIARG_VIDEODECODERBEGINFRAME
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
req.iface: 
---

# D3D11_1DDIARG_VIDEODECODERBEGINFRAME structure



## -description
<p>Specifies a content key in a call to the <a href="display.videodecoderbeginframe">VideoDecoderBeginFrame</a>  function.</p>


## -syntax

````
typedef struct D3D11_1DDIARG_VIDEODECODERBEGINFRAME {
  D3D11_1DDI_HVIDEODECODEROUTPUTVIEW hOutputView;
  const void                         *pContentKey;
  UINT                               ContentKeySize;
} D3D11_1DDIARG_VIDEODECODERBEGINFRAME;
````


## -struct-fields
<dl>

### -field hOutputView

<dd>
<p>A handle to the driver's private data for the video decoder output view. This handle was created through a call to the <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-createvideoprocessoroutputview.md">CreateVideoProcessorOutputView</a> function.</p>
</dd>

### -field pContentKey

<dd>
<p>A pointer to a content key that was used to encrypt the video frame data. If no content key was used, set this member to <b>NULL</b>. If the caller provides a content key, the caller must use the session key to encrypt the content key.</p>
<p>For more information, see the <a href="display.videodecoderbeginframe">VideoDecoderBeginFrame</a> function.</p>
</dd>

### -field ContentKeySize

<dd>
<p>The size, in bytes, of the content key that is specified in the <b>pContentKey</b> member.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 8</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11-1ddi-createvideoprocessoroutputview.md">CreateVideoProcessorOutputView</a>
</dt>
<dt>
<a href="display.videodecoderbeginframe">VideoDecoderBeginFrame</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDIARG_VIDEODECODERBEGINFRAME structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
