---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES
title: PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES
author: windows-driver-content
description: Queries the driver for video capabilities. Required for Windows Display Driver Model (WDDM) 2.0 or later drivers.
old-location: display\queryvideocapabilities.htm
old-project: display
ms.assetid: C86C7D1C-541F-4EC3-B4C8-126826BE3529
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SETRESULT_INFO, *PSETRESULT_INFO, SETRESULT_INFO
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
req.alt-api: pfnQueryVideoCapabilities
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
req.typenames: *PSETRESULT_INFO, SETRESULT_INFO
---

# PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES callback



## -description
Queries the driver for video capabilities. Required for Windows Display Driver Model (WDDM) 2.0 or later drivers.



## -prototype

````
PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES pfnQueryVideoCapabilities;

VOID APIENTRY* pfnQueryVideoCapabilities(
  _In_    D3D10DDI_HDEVICE                     hDevice,
  _In_    D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY QueryType,
  _In_    UINT                                 DataSize,
  _Inout_ VOID                                 *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param QueryType [in]

Specifies the <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY</a> value indicating the type of data being queried.


### -param DataSize [in]

Specifies the size of the <b>pData</b> member. This is dependent on the <b>QueryType</b> member.


### -param pData [in, out]


Pointer to a structure containing data further identifying input parameters and output parameters to be filled in by the driver. The following structures are supported for the following query types:




### -param D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_CAPS

<b>pData</b> points to a <a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_video_decoder_caps.md">D3DWDDM2_0DDI_VIDEO_DECODER_CAPS</a> structure.


### -param D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_DECODER_DOWNSAMPLING

<b>pData</b> points to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a> structure.


### -param D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY_RECOMMENDED_DECODER_DOWNSAMPLING

<b>pData</b> points to a <a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a> structure.

</dd>
</dl>

## -returns
This callback function does not return a value.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

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
<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_video_capability_query.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_QUERY</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3dwddm2_0ddi_video_decoder_caps.md">D3DWDDM2_0DDI_VIDEO_DECODER_CAPS</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_DECODER_DOWNSAMPLING</a>
</dt>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm2_0ddi_video_capability_recommend_decoder_downsampling.md">D3DWDDM2_0DDI_VIDEO_CAPABILITY_RECOMMEND_DECODER_DOWNSAMPLING</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_QUERYVIDEOCAPABILITIES callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

