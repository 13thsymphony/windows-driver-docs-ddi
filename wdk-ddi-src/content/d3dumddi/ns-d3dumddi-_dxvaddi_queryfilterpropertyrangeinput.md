---
UID: NS.D3DUMDDI._DXVADDI_QUERYFILTERPROPERTYRANGEINPUT
title: _DXVADDI_QUERYFILTERPROPERTYRANGEINPUT
author: windows-driver-content
description: The DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure describes a filter setting on a video stream that range information is requested for.
old-location: display\dxvaddi_queryfilterpropertyrangeinput.htm
old-project: display
ms.assetid: d073d326-6cc6-4216-b312-809d707aef3b
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXVADDI_QUERYFILTERPROPERTYRANGEINPUT, DXVADDI_QUERYFILTERPROPERTYRANGEINPUT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVADDI_QUERYFILTERPROPERTYRANGEINPUT
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
---

# _DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure



## -description
The DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure describes a filter setting on a video stream that range information is requested for.



## -syntax

````
typedef struct _DXVADDI_QUERYFILTERPROPERTYRANGEINPUT {
  const GUID        *pVideoProcGuid;
  DXVADDI_VIDEODESC VideoDesc;
  D3DDDIFORMAT      RenderTargetFormat;
  UINT              FilterSetting;
} DXVADDI_QUERYFILTERPROPERTYRANGEINPUT;
````


## -struct-fields

### -field pVideoProcGuid

[in] A pointer to a GUID that represents the video processing device type. 


### -field VideoDesc

[in] A <a href="display.dxvaddi_videodesc">DXVADDI_VIDEODESC</a> structure that describes the video stream.


### -field RenderTargetFormat

[in] A <a href="display.d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the render target for the video processing device.


### -field FilterSetting

[in] A filter setting that range information is requested for. This member can be one of the following settings:

<ul>
<li>
DXVADDI_NOISEFILTER_LUMALEVEL

</li>
<li>
DXVADDI_NOISEFILTER_LUMATHREASHOLD

</li>
<li>
DXVADDI_NOISEFILTER_LUMARADIUS

</li>
<li>
DXVADDI_NOISEFILTER_CHROMALEVEL

</li>
<li>
DXVADDI_NOISEFILTER_CHROMATHREASHOLD

</li>
<li>
DXVADDI_NOISEFILTER_CHROMARADIUS

</li>
<li>
DXVADDI_DETAILFILTER_LUMALEVEL

</li>
<li>
DXVADDI_DETAILFILTER_LUMATHREASHOLD

</li>
<li>
DXVADDI_DETAILFILTER_LUMARADIUS

</li>
<li>
DXVADDI_DETAILFILTER_CHROMALEVEL

</li>
<li>
DXVADDI_DETAILFILTER_CHROMATHREASHOLD

</li>
<li>
DXVADDI_DETAILFILTER_CHROMARADIUS

</li>
</ul>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating systems.

</td>
</tr>
<tr>
<th width="30%">
Header

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
<a href="display.d3dddiarg_getcaps">D3DDDIARG_GETCAPS</a>
</dt>
<dt>
<a href="display.d3dddicaps_type">D3DDDICAPS_TYPE</a>
</dt>
<dt>
<a href="display.dxvaddi_valuerange">DXVADDI_VALUERANGE</a>
</dt>
<dt>
<a href="display.dxvaddi_videodesc">DXVADDI_VIDEODESC</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_getcaps.md">GetCaps</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVADDI_QUERYFILTERPROPERTYRANGEINPUT structure%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

