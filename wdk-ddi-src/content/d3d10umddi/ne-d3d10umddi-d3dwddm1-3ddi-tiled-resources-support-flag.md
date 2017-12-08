---
UID: NE.d3d10umddi.D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
title: D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
author: windows-driver-content
description: Indicates the level of support by the hardware and user-mode display driver for tiled resources.
old-location: display\d3dwddm1_3ddi_tiled_resources_support_flag.htm
old-project: display
ms.assetid: 5EEF8C68-0DE7-466B-946F-37157B21C9B7
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: SETRESULT_INFO, SETRESULT_INFO, *PSETRESULT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
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

# D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG enumeration



## -description
<p>Indicates the level of support by the hardware and user-mode display driver for tiled resources.</p>


## -syntax

````
typedef enum _D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG { 
  D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED  = 0x00000001,
  D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED  = 0x00000002
} D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG;
````


## -enum-fields
<dl>

### -field D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED

<dd>
<p>Tiled resources are supported to a  minimal level.</p>
</dd>

### -field D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED

<dd>
<p>Tiled resources are supported to a greater extent than for <b>D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED</b>.</p>
<p>If this flag is set, the Direct3D runtime assumes that the support level of the <b>D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED</b> flag also applies.</p>
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
<p>Windows 8.1</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2012 R2</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>WDDM 1.3</p>
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
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1-3ddi-d3d11-options-data1.md">D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG enumeration%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
