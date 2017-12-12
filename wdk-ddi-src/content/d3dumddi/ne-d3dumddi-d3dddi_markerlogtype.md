---
UID: NE.d3dumddi.D3DDDI_MARKERLOGTYPE
title: D3DDDI_MARKERLOGTYPE
author: windows-driver-content
description: Indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.
old-location: display\d3dddi_markerlogtype.htm
old-project: display
ms.assetid: CBD48828-7DAA-470F-AB9E-34957C579EB5
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: D3DDDI_MARKERLOGTYPE, D3DDDI_MARKERLOGTYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dumddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MARKERLOGTYPE
req.alt-loc: D3dumddi.h
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

# D3DDDI_MARKERLOGTYPE enumeration



## -description
Indicates the type of marker in the Event Tracing for Windows (ETW) log that the user-mode display driver supports.



## -syntax

````
typedef enum D3DDDI_MARKERLOGTYPE { 
  D3DDDIMLT_NONE,
  D3DDDIMLT_PROFILE,
  D3DDDIMLT_FT_PROFILE
} D3DDDI_MARKERLOGTYPE;
````


## -enum-fields

### -field D3DDDIMLT_NONE

No marker type is supported. In this case, the marker type of submitted commands must be <a href="..\d3dumddi\ne-d3dumddi-d3dddi_markertype.md">D3DDDI_MARKERTYPE</a>.<b>D3DDDIMT_NONE</b>.


### -field D3DDDIMLT_PROFILE

The context submits GPU work for single-threaded user-mode DDIs. In this case, each time stamp denotes the end of GPU work.


### -field D3DDDIMLT_FT_PROFILE

The context submits GPU work for free-threaded user-mode DDIs. In this case, the driver must have set the <b>Caps</b> member of the <a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a> structure to <b>D3D11DDICAPS_FREETHREADED</b>.


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
Header

</th>
<td width="70%">
<dl>
<dt>D3dumddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3d10umddi\ns-d3d10umddi-d3d11ddi_threading_caps.md">D3D11DDI_THREADING_CAPS</a>
</dt>
<dt>
<a href="..\d3dumddi\ne-d3dumddi-d3dddi_markertype.md">D3DDDI_MARKERTYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DDDI_MARKERLOGTYPE enumeration%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

