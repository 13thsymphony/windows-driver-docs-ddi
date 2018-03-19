---
UID: NC:d3dumddi.PFND3DDDI_MAPGPUVIRTUALADDRESSCB
title: PFND3DDDI_MAPGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnMapGpuVirtualAddressCb maps graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state.
old-location: display\pfnmapgpuvirtualaddresscb.htm
old-project: display
ms.assetid: DA67A98C-BE9C-412D-9382-CAC5B05FEE3B
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_MAPGPUVIRTUALADDRESSCB, d3dumddi/pfnMapGpuVirtualAddressCb, display.pfnmapgpuvirtualaddresscb, pfnMapGpuVirtualAddressCb, pfnMapGpuVirtualAddressCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnMapGpuVirtualAddressCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---


# PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback function
<b>pfnMapGpuVirtualAddressCb</b> maps graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the <i>Invalid</i> or <i>Zero</i> state. The user mode driver can specify a specific base GPU virtual address to map or let the video memory manager automatically pick one. 
When specifying a non-NULL <b>BaseAddress</b> value, the entire range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>Size</b> must be in a freed state or belong to a virtual address range, obtained by calling <b>pfnMapGpuVirtualAddressCb</b> or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>. Note that when <b>Protection.Zero</b> or <b>Protection.NoAccess</b> is specified, the virtual address range cannot belong to a range, obtained by calling <b>pfnMapGpuVirtualAddressCb</b>.
The user mode driver  may specify if the mapping should allow for write &amp; execute privileges in addition to read privileges, which always exist by default. 
In LDA configuration the paging queue defines a physical GPU, whose page tables are modified, and the allocation handle (if not NULL) defines where the page table entries are pointing to. The allocation can be resident in any physical GPU memory segment.

## Syntax

```
PFND3DDDI_MAPGPUVIRTUALADDRESSCB Pfnd3dddiMapgpuvirtualaddresscb;

HRESULT Pfnd3dddiMapgpuvirtualaddresscb(
  HANDLE hDevice,
  D3DDDI_MAPGPUVIRTUALADDRESS *
)
{...}
```

## Parameters

`hDevice`

A handle to the display device.

`*`




## Return Value

<b>pfnMapGpuVirtualAddressCb</b> returns one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>S_OK</b></dt>
</dl>
</td>
<td width="60%">
The operation completed successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>E_PENDING </b></dt>
</dl>
</td>
<td width="60%">
The call was successful, but the operation is not finished. The caller must wait for the returned fence value before accessing the allocation.

</td>
</tr>
</table>
 

This function might also return other values.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Desktop |
| **Header** | d3dumddi.h (include D3dumddi.h) |

## See Also

<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md">D3DDDI_MAPGPUVIRTUALADDRESS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>