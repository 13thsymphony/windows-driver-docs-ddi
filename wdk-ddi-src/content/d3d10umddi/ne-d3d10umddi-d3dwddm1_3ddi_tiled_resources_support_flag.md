---
UID: NE.d3d10umddi.D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
title: D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
author: windows-driver-content
description: Indicates the level of support by the hardware and user-mode display driver for tiled resources.
old-location: display\d3dwddm1_3ddi_tiled_resources_support_flag.htm
old-project: display
ms.assetid: 5EEF8C68-0DE7-466B-946F-37157B21C9B7
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG, D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG
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
---

# D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG enumeration



## -description
Indicates the level of support by the hardware and user-mode display driver for tiled resources.



## -syntax

````
typedef enum _D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG { 
  D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED  = 0x00000001,
  D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED  = 0x00000002
} D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG;
````


## -enum-fields

### -field D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED

Tiled resources are supported to a  minimal level.


### -field D3DWDDM1_3DDI_TILED_RESOURCES_TIER_2_SUPPORTED

Tiled resources are supported to a greater extent than for <b>D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED</b>.

If this flag is set, the Direct3D runtime assumes that the support level of the <b>D3DWDDM1_3DDI_TILED_RESOURCES_TIER_1_SUPPORTED</b> flag also applies.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 8.1

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012 R2

</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
WDDM 1.3

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
<a href="..\d3d10umddi\ns-d3d10umddi-d3dwddm1_3ddi_d3d11_options_data1.md">D3DWDDM1_3DDI_D3D11_OPTIONS_DATA1</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DWDDM1_3DDI_TILED_RESOURCES_SUPPORT_FLAG enumeration%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

