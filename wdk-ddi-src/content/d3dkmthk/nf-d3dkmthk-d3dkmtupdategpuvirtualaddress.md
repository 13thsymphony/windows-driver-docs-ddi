---
UID: NF.d3dkmthk.D3DKMTUpdateGpuVirtualAddress
title: D3DKMTUpdateGpuVirtualAddress function
author: windows-driver-content
description: D3DKMTUpdateGpuVirtualAddress is a special operation used in the context of tile resources. It allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates.
old-location: display\d3dkmtupdategpuvirtualaddress.htm
old-project: display
ms.assetid: 3390A01D-BD4B-4399-AA3E-91BB32264A13
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: D3DKMTUpdateGpuVirtualAddress
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: D3DKMTUpdateGpuVirtualAddress
req.alt-loc: GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-1.dll,GDI32.dll,API-MS-Win-DX-D3DKMT-L1-1-2.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: GDI32.lib
req.dll: GDI32.dll
req.irql: 
---

# D3DKMTUpdateGpuVirtualAddress function



## -description
<b>D3DKMTUpdateGpuVirtualAddress</b> is a special operation used in the context of tile resources. It allows the driver to specify a number of mapping operations to be applied to the process virtual address space in a single batch of page table updates. 



## -syntax

````
NTSTATUS APIENTRY D3DKMTUpdateGpuVirtualAddress(
  _In_ const D3DKMT_UPDATEGPUVIRTUALADDRESS *pData
);
````


## -parameters

### -param pData [in]

A pointer to a <a href="display.d3dkmt_updategpuvirtualaddress">D3DKMT_UPDATEGPUVIRTUALADDRESS</a> structure that describes the operation.

## -returns
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>The device context was successfully created.
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>Parameters were validated and determined to be incorrect.

 

This function might also return other <b>NTSTATUS</b> values.

## -remarks
The range of graphics processing unit (GPU) virtual addresses in all operations (except the source of the copy operations) must belong to a single virtual address range which was obtained by calling <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md">ReserveGpuVirtualAddressRange</a>.   Similarly, the virtual address ranges of all sources in copy operations must belong to a single virtual address range, which was obtained by calling <i>ReserveGpuVirtualAddressRange</i>.

The page table updates are executed on a paging context, dedicated to the rendering context specified, and executed on the GPU only after the associated rendering context signaled <b>FenceValue</b> for the specified monitored fence object. When the page table updates are finished, the paging context signals the monitored fence object to <b>FenceValue</b>+1, allowing the rendering context to do tight interlocking with the page table updates.

The virtual address ranges in the update operations are allowed to intersect. The operations will be applied in the order they are submitted.

In a single <b>UpdateVirtualAddress</b> call:

Drivers can submit many <b>UpdateGpuVirtualAddress</b> calls, which will be queued behind the rendering fence. When the number of queued update operations exceeds 128, the calling thread will be blocked until the pervious operations are processed by the video memory manager.

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
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>D3dkmthk.h (include D3dkmthk.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>GDI32.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL
</th>
<td width="70%">
<dl>
<dt>GDI32.dll</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="display.d3dkmt_updategpuvirtualaddress">D3DKMT_UPDATEGPUVIRTUALADDRESS</a>
</dt>
<dt>
<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_reservegpuvirtualaddressrange.md">ReserveGpuVirtualAddressRange</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMTUpdateGpuVirtualAddress function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
