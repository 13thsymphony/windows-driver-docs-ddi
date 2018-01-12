---
UID: NS:d3dumddi.D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
title: D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO
author: windows-driver-content
description: Specifies info about a multiplane overlay allocation.
old-location: display\d3dddi_multiplane_allocation_info.htm
old-project: display
ms.assetid: ce3610ab-a927-45e7-8ceb-3f38b5f50f00
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO, D3DDDI_MULTIPLANE_ALLOCATION_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DDDI_MULTIPLANE_ALLOCATION_INFO
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
req.typenames: D3DDDI_MULTIPLANE_ALLOCATION_INFO
---

# D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO structure



## -description
Specifies info about a multiplane overlay allocation.



## -syntax

````
typedef struct D3DDDI_MULTIPLANE_OVERLAY_ALLOCATION_INFO {
  D3DKMT_HANDLE PresentAllocation;
  UINT          SubResourceIndex;
} D3DDDI_MULTIPLANE_ALLOCATION_INFO;
````


## -struct-fields

### -field PresentAllocation

[in] A handle to the multiplane overlay allocation.


### -field SubResourceIndex

[in] The zero-based index into the resource which the handle in the <b>PresentAllocation</b> member specifies. This index indicates the display surface.


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>