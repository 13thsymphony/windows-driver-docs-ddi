---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE
title: PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE
author: windows-driver-content
description: Sets the color space information for the video processor output surface. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.
old-location: display\videoprocessorsetoutputshaderusage.htm
old-project: display
ms.assetid: 320618F6-DE98-45D0-8015-DE24689D24D2
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
req.alt-api: pfnVideoProcessorSetOutputShaderUsage
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

# PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE callback



## -description
Sets the color space information for the video processor output surface. Optional for Windows Display Driver Model (WDDM) 2.0, or later, drivers.



## -prototype

````
PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE pfnVideoProcessorSetOutputShaderUsage;

VOID APIENTRY* pfnVideoProcessorSetOutputShaderUsage(
  _In_ D3D10DDI_HDEVICE           hDevice,
  _In_ D3D11_1DDI_HVIDEOPROCESSOR hVideoProcessor,
  _In_ BOOL                       ShaderUsage
)
{ ... }
````


## -parameters

### -param hDevice [in]

 A handle to the display device (graphics context). The Direct3D runtime passed the user-mode driver this handle as the <b>hDevice</b> member of the <a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a> structure at device creation.


### -param hVideoProcessor [in]

A handle to the video processor object. 


### -param ShaderUsage [in]

Indicates whether the output of <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a> may be read by Direct3D shaders.

<div class="alert"><b>Note</b>  This will always be <b>TRUE</b> unless multi-plane overlay hardware exists.</div>
<div> </div>

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
<a href="..\d3dumddi\ns-d3dumddi-_d3dddiarg_createdevice.md">D3DDDIARG_CREATEDEVICE</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d11_1ddi_videoprocessorblt.md">VideoProcessorBlt</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DWDDM2_0DDI_VIDEOPROCESSORSETOUTPUTSHADERUSAGE callback function%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

