---
UID: NS:dxgiddi.DXGI_DDI_ARG_PRESENTSURFACE
title: DXGI_DDI_ARG_PRESENTSURFACE
author: windows-driver-content
description: Describes a surface to display.
old-location: display\dxgi_ddi_arg_presentsurface.htm
old-project: display
ms.assetid: 1A1E2644-7411-4D69-8D45-B19D707221AB
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: DXGI_DDI_ARG_PRESENTSURFACE, DXGI_DDI_ARG_PRESENTSURFACE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxgiddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1,WDDM 1.3 and later
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGI_DDI_ARG_PRESENTSURFACE
req.alt-loc: Dxgiddi.h
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
req.typenames: DXGI_DDI_ARG_PRESENTSURFACE
---

# DXGI_DDI_ARG_PRESENTSURFACE structure



## -description
Describes a surface to display.



## -syntax

````
typedef struct DXGI_DDI_ARG_PRESENTSURFACE {
  DXGI_DDI_HRESOURCE hSurface;
  UINT               SubResourceIndex;
} DXGI_DDI_ARG_PRESENTSURFACE;
````


## -struct-fields

### -field hSurface

[in] A handle to the resource that contains the surface. 


### -field SubResourceIndex

The zero-based index into the resource, which the handle in the <b>hSurface</b> member specifies. The <b>SubResourceIndex</b> index indicates the surface.


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
WDDM 1.3 and later

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dxgiddi.h (include D3d10umddi.h)</dt>
</dl>
</td>
</tr>
</table>