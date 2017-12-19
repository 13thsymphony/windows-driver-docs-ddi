---
UID: NS.D3D10UMDDI.D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
title: D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
author: windows-driver-content
description: Specifies the attributes of a video processor enumeration object.
old-location: display\d3d11_1ddiarg_createvideoprocessorenum.htm
old-project: display
ms.assetid: 7edcd852-429f-4059-92bb-99c7874a9357
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM, D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
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
req.alt-api: D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM
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

# D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM structure



## -description
Specifies the attributes of a video processor enumeration object.



## -syntax

````
typedef struct D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM {
  D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC Desc;
} D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM;
````


## -struct-fields

### -field Desc

A <a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_content_desc.md">D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC</a> structure that describes a video stream for a video processor.


## -remarks


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
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11_1ddi_video_processor_content_desc.md">D3D11_1DDI_VIDEO_PROCESSOR_CONTENT_DESC</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11_1DDIARG_CREATEVIDEOPROCESSORENUM structure%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

