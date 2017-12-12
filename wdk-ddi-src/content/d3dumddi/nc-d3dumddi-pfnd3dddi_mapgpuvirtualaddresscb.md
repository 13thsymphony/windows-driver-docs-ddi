---
UID: NC.d3dumddi.PFND3DDDI_MAPGPUVIRTUALADDRESSCB
title: PFND3DDDI_MAPGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnMapGpuVirtualAddressCb maps graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the Invalid or Zero state.
old-location: display\pfnmapgpuvirtualaddresscb.htm
old-project: display
ms.assetid: DA67A98C-BE9C-412D-9382-CAC5B05FEE3B
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _DXGK_PTE, DXGK_PTE
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
req.alt-api: pfnMapGpuVirtualAddressCb
req.alt-loc: d3dumddi.h
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

# PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback



## -description
<b>pfnMapGpuVirtualAddressCb</b> maps graphics processing unit (GPU) virtual address ranges to a specific allocation range or puts it to the <i>Invalid</i> or <i>Zero</i> state. The user mode driver can specify a specific base GPU virtual address to map or let the video memory manager automatically pick one. 
When specifying a non-NULL <b>BaseAddress</b> value, the entire range from <b>BaseAddress</b> to <b>BaseAddress</b>+<b>Size</b> must be in a freed state or belong to a virtual address range, obtained by calling <b>pfnMapGpuVirtualAddressCb</b> or <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>. Note that when <b>Protection.Zero</b> or <b>Protection.NoAccess</b> is specified, the virtual address range cannot belong to a range, obtained by calling <b>pfnMapGpuVirtualAddressCb</b>.
The user mode driver  may specify if the mapping should allow for write &amp; execute privileges in addition to read privileges, which always exist by default. 
In LDA configuration the paging queue defines a physical GPU, whose page tables are modified, and the allocation handle (if not NULL) defines where the page table entries are pointing to. The allocation can be resident in any physical GPU memory segment.




## -prototype

````
PFND3DDDI_MAPGPUVIRTUALADDRESSCB pfnMapGpuVirtualAddressCb;

HRESULT APIENTRY CALLBACK* pfnMapGpuVirtualAddressCb(
  _In_    HANDLE                      hDevice,
  _Inout_ D3DDDI_MAPGPUVIRTUALADDRESS *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device.


### -param pData [in, out]

A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md">D3DDDI_MAPGPUVIRTUALADDRESS</a> structure that describes the operation to perform.




## -returns
<b>pfnMapGpuVirtualAddressCb</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The operation completed successfully.
<dl>
<dt><b>E_PENDING </b></dt>
</dl>The call was successful, but the operation is not finished. The caller must wait for the returned fence value before accessing the allocation.

 

This function might also return other values.


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
<dt>D3dumddi.h (include D3dumddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>
</dt>
<dt>
<a href="..\d3dukmdt\ns-d3dukmdt-d3dddi_mapgpuvirtualaddress.md">D3DDDI_MAPGPUVIRTUALADDRESS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_MAPGPUVIRTUALADDRESSCB callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

