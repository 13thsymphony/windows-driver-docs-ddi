---
UID: NS.D3DKMDDI._DXGKARGCB_MAPCONTEXTALLOCATION
title: _DXGKARGCB_MAPCONTEXTALLOCATION
author: windows-driver-content
description: DXGKARGCB_MAPCONTEXTALLOCATION is used with DxgkCbMapContextAllocation to map a graphics processing unit (GPU) virtual address to the specified context allocation.
old-location: display\dxgkargcb_mapcontextallocation.htm
old-project: display
ms.assetid: F26E382F-D9F8-4452-983E-4523A77ADC35
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _DXGKARGCB_MAPCONTEXTALLOCATION, DXGKARGCB_MAPCONTEXTALLOCATION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXGKARGCB_MAPCONTEXTALLOCATION
req.alt-loc: d3dkmddi.h
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
---

# _DXGKARGCB_MAPCONTEXTALLOCATION structure



## -description
<b>DXGKARGCB_MAPCONTEXTALLOCATION</b> is used with <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_mapcontextallocation.md">DxgkCbMapContextAllocation</a> to map a graphics processing unit (GPU) virtual address to the specified context allocation.


## -syntax

````
typedef struct _DXGKARGCB_MAPCONTEXTALLOCATION {
  D3DGPU_VIRTUAL_ADDRESS                  BaseAddress;
  D3DGPU_VIRTUAL_ADDRESS                  MinimumAddress;
  D3DGPU_VIRTUAL_ADDRESS                  MaximumAddress;
  HANDLE                                  hAllocation;
  D3DGPU_SIZE_T                           OffsetInPages;
  D3DGPU_SIZE_T                           SizeInPages;
  D3DDDIGPUVIRTUALADDRESS_PROTECTION_TYPE Protection;
  UINT64                                  DriverProtection;
} DXGKARGCB_MAPCONTEXTALLOCATION;
````


## -struct-fields

### -field BaseAddress

(optional) If non-NULL, the video memory manager will attempt to use this address as the base address for the mapping. If the range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>Size</b> isn’t free, the call will fail. When this parameter is non-NULL, <b>MinimumAddress</b> and <b>MaximumAddress</b> are ignored.


If NULL is specified, the video memory manager will pick the base address for the allocation within the specified <b>MinimumAddress</b> and <b>MaximumAddress</b>. 


### -field MinimumAddress

(optional) Specifies the minimum GPU virtual address to consider for the mapped range. 

This parameter is ignored when <b>BaseAddress</b> != <b>NULL</b>.


### -field MaximumAddress

Specifies the maximum GPU virtual address to consider for the mapped range. The video memory manager will guarantee that <b>BaseAddress</b>+<b>Size</b> &lt;= <b>MaximumAddress</b>. If this is set to <b>NULL</b> the video memory manager will not apply any limit.

This parameter is ignored when <b>BaseAddress</b> != <b>NULL</b>.


### -field hAllocation

Handle to the allocation being mapped into the GPU virtual address space. This is a DirectX graphics kernel  handle, returned by <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>.

### -field OffsetInPages

Specifies the offset, in 4KB pages, to the starting page within the specified allocation that must be mapped.

### -field SizeInPages

Specifies the size of the range to map in number of 4KB pages.

### -field Protection

Specifies the protection on the GPU virtual address that is mapped. 

### -field DriverProtection

Specifies the driver protection parameters.

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
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_createcontextallocation.md">DxgkCbCreateContextAllocation</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_mapcontextallocation.md">DxgkCbMapContextAllocation</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARGCB_MAPCONTEXTALLOCATION structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
