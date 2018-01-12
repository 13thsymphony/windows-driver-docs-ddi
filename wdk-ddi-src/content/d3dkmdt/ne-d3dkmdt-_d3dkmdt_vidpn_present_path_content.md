---
UID: NE:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
title: _D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration is used to indicate the type of content that is displayed on a VidPN present path.
old-location: display\d3dkmdt_vidpn_present_path_content.htm
old-project: display
ms.assetid: 29423933-c3cf-4fe4-b79c-f82718163a23
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _D3DKMDT_VIDPN_PRESENT_PATH_CONTENT, D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
req.alt-loc: d3dkmdt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH_CONTENT
---

# _D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration



## -description
The D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration is used to indicate the type of content that is displayed on a VidPN present path.



## -syntax

````
typedef enum _D3DKMDT_VIDPN_PRESENT_PATH_CONTENT { 
  D3DKMDT_VPPC_UNINITIALIZED  = 0,
  D3DKMDT_VPPC_GRAPHICS       = 1,
  D3DKMDT_VPPC_VIDEO          = 2,
  D3DKMDT_VPPC_NOTSPECIFIED   = 255
} D3DKMDT_VIDPN_PRESENT_PATH_CONTENT;
````


## -enum-fields

### -field D3DKMDT_VPPC_UNINITIALIZED

Indicates that a variable of type D3DKMDT_VIDPN_PRESENT_PATH_CONTENT has not yet been assigned a meaningful value.


### -field D3DKMDT_VPPC_GRAPHICS

Indicates that the path displays graphics content.


### -field D3DKMDT_VPPC_VIDEO

Indicates that the path displays video content.


### -field D3DKMDT_VPPC_NOTSPECIFIED

Indicates that no content type has been specified.


## -remarks
The <b>Content</b> member of a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path.md">D3DKMDT_VIDPN_PRESENT_PATH</a> structure is a value from the D3DKMDT_VIDPN_PRESENT_PATH_CONTENT enumeration.


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
<dt>D3dkmdt.h (include D3dkmdt.h)</dt>
</dl>
</td>
</tr>
</table>