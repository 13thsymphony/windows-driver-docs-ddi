---
UID: NS.d3dumddi._D3DDDIARG_CREATEVIDEOPROCESSDEVICE
title: D3DDDIARG_CREATEVIDEOPROCESSDEVICE
author: windows-driver-content
description: The D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processing device to create.
old-location: display\d3dddiarg_createvideoprocessdevice.htm
ms.assetid: b875755c-9559-41ee-8a9b-1de05a2f1dab
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: display
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDIARG_CREATEVIDEOPROCESSDEVICE
req.alt-loc: d3dumddi.h
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
ms.keywords: D3DDDIARG_CREATEVIDEOPROCESSDEVICE, D3DDDIARG_CREATEVIDEOPROCESSDEVICE
req.iface: 
---

# D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure



## -description
<p>The D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure describes a Microsoft DirectX Video Acceleration (DirectX VA) video processing device to create. </p>


## -syntax

````
typedef struct _D3DDDIARG_CREATEVIDEOPROCESSDEVICE {
  const GUID        *pVideoProcGuid;
  DXVADDI_VIDEODESC VideoDesc;
  D3DDDIFORMAT      RenderTargetFormat;
  UINT              MaxSubStreams;
  HANDLE            hVideoProcess;
} D3DDDIARG_CREATEVIDEOPROCESSDEVICE;
````


## -struct-fields
<dl>

### -field <b>pVideoProcGuid</b>

<dd>
<p>[in] A pointer to the GUID that represents a DirectX VA video processing device to create. The Microsoft Direct3D runtime can call the user-mode display driver's <a href="https://msdn.microsoft.com/cf6c61ce-7b53-46d0-b3ff-ed5b2b964c65">GetCaps</a> function to query for the video processing GUIDs that the driver supports. </p>
</dd>

### -field <b>VideoDesc</b>

<dd>
<p>[in] The <a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a> structure for the video stream that the video processing device should process.</p>
</dd>

### -field <b>RenderTargetFormat</b>

<dd>
<p>[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff544312">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.</p>
</dd>

### -field <b>MaxSubStreams</b>

<dd>
<p>[in] The maximum number of video substreams that can be sent to the video processing device. If this value is set to zero, the device never receives any video substreams.</p>
</dd>

### -field <b>hVideoProcess</b>

<dd>
<p>[in/out] A handle to the video processing device. The user-mode display driver must set this handle to a value that the Microsoft Direct3D runtime can use to identify the video processing device in subsequent calls.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available in Windows Vista and later versions of the Windows operating systems.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/3149c7d9-0bf7-4355-8f15-821cf6b92f0a">CreateVideoProcessDevice</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff562944">DXVADDI_VIDEODESC</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDIARG_CREATEVIDEOPROCESSDEVICE structure%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
