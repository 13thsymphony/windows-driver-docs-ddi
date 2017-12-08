---
UID: NS.d3d10umddi.D3D11DDI_3DPIPELINESUPPORT_CAPS
title: D3D11DDI_3DPIPELINESUPPORT_CAPS
author: windows-driver-content
description: The D3D11DDI_3DPIPELINESUPPORT_CAPS structure contains display device pipeline capabilities.
old-location: display\d3d11ddi_3dpipelinesupport_caps.htm
old-project: display
ms.assetid: 69bafa36-2f99-4c6f-b5ed-99a7030b22e6
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: D3D11DDI_3DPIPELINESUPPORT_CAPS, D3D11DDI_3DPIPELINESUPPORT_CAPS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: D3D11DDI_3DPIPELINESUPPORT_CAPS is supported beginning with the Windows 7 operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3D11DDI_3DPIPELINESUPPORT_CAPS
req.alt-loc: d3d10umddi.h
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

# D3D11DDI_3DPIPELINESUPPORT_CAPS structure



## -description
<p>The D3D11DDI_3DPIPELINESUPPORT_CAPS structure contains display device pipeline capabilities. </p>


## -syntax

````
typedef struct D3D11DDI_3DPIPELINESUPPORT_CAPS {
  UINT Caps;
} D3D11DDI_3DPIPELINESUPPORT_CAPS;
````


## -struct-fields
<dl>

### -field Caps

<dd>
<p>[in] A value that identifies the pipeline capabilities of the driver. </p>
</dd>
</dl>

## -remarks
<p>The driver uses the one of the values from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi-3dpipelinelevel.md">D3D11DDI_3DPIPELINELEVEL</a> enumeration and the following macro to encode the 3-D pipeline level:</p>

<p>The driver then uses the macro's result in the <b>Caps</b> member of the D3D11DDI_3DPIPELINESUPPORT_CAPS structure to provide information to the Direct3D runtime when the runtime calls the driver's <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10-2ddi-getcaps.md">GetCaps(D3D10_2)</a> function with the <b>Type</b> member of <a href="..\d3d10umddi\ns-d3d10umddi-d3d10-2ddiarg-getcaps.md">D3D10_2DDIARG_GETCAPS</a> set to D3D11DDICAPS_3DPIPELINESUPPORT.</p>

<p>The driver uses the following constant and macros to extract one of the values from the <a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi-3dpipelinelevel.md">D3D11DDI_3DPIPELINELEVEL</a> enumeration that represents the 3-D pipeline level to set for a display device. The driver extracts the value from the <b>Caps</b> member of the D3D11DDI_3DPIPELINESUPPORT_CAPS structure. The driver uses the 3-D pipeline level to create the appropriate display device when the driver receives a call to its <a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a> function.</p>

<p>For more information about the Direct3D version 10 pipeline, see <a href="https://msdn.microsoft.com/63672d6e-5c5d-4873-a104-991e0b17d128">Rendering Pipeline</a>. </p>

<p>For more information about the Direct3D version 11 pipelines, see <a href="https://msdn.microsoft.com/7d724751-761e-409c-8398-d1b5d58c057c">Pipelines for Direct3D Version 11</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>D3D11DDI_3DPIPELINESUPPORT_CAPS is supported beginning with the Windows 7 operating system. </p>
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
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10ddi-createdevice.md">CreateDevice(D3D10)</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d10-2ddicaps-type.md">D3D10_2DDICAPS_TYPE</a>
</dt>
<dt>
<a href="..\d3d10umddi\ne-d3d10umddi-d3d11ddi-3dpipelinelevel.md">D3D11DDI_3DPIPELINELEVEL</a>
</dt>
<dt>
<a href="..\d3d10umddi\nc-d3d10umddi-pfnd3d10-2ddi-getcaps.md">GetCaps(D3D10_2)</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3D11DDI_3DPIPELINESUPPORT_CAPS structure%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
