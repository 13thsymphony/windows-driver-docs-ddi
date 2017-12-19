---
UID: NC.d3dumddi.PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB
title: PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnUpdateGpuVirtualAddressCb is a special operation used in the context of tile resources.
old-location: display\pfnupdategpuvirtualaddresscb.htm
old-project: display
ms.assetid: 99D075A0-4483-47D1-BA24-80C45BFF407A
ms.author: windowsdriverdev
ms.date: 12/15/2017
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
req.alt-api: pfnUpdateGpuVirtualAddressCb
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

# PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB callback



## -description
<b>pfnUpdateGpuVirtualAddressCb</b> is a special operation used in the context of tile resources. It allows the user mode driver to specify a number of mapping operations to be applied to the process' virtual address space in a single batch of page table updates. 


The range of graphics processing unit (GPU) virtual addresses in all operations (except for the source address of copy operations) must belong to a single virtual address range that was obtained by calling <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>.   Similarly, the virtual address ranges of all sources in copy operations must belong to a single virtual address range, which was obtained by calling <i>pfnReserveGpuVirtualAddressCb</i>.

The page table updates are executed on a paging context, dedicated to the rendering context specified, and executed on the GPU only after the associated rendering context signaled <b>FenceValue</b> for the specified monitored fence object. When the page table updates are finished, the paging context signals the monitored fence object to <b>FenceValue</b>+1, allowing the rendering context to do tight interlocking with the page table updates.



## -prototype

````
PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB pfnUpdateGpuVirtualAddressCb;

HRESULT APIENTRY CALLBACK* pfnUpdateGpuVirtualAddressCb(
  _In_ HANDLE                           hDevice,
  _In_ D3DDDICB_UPDATEGPUVIRTUALADDRESS *pData
)
{ ... }
````


## -parameters

### -param hDevice [in]

A handle to the display device.


### -param pData [in]

A pointer to a <a href="display.d3dddicb_updategpuvirtualaddress">D3DDDICB_UPDATEGPUVIRTUALADDRESS</a> structure that describes the operation to perform.




## -returns
If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.


## -remarks
The virtual address ranges in the update operations are allowed to intersect. The operations will be applied in the order they are submitted.

In a single <b>pfnUpdateVirtualAddressCb</b> call:

The user mode driver can submit many <b>pfnUpdateGpuVirtualAddressCb</b> calls and operations will be queued behind the rendering fence. When the number of queued update operations exceeds 128, the calling thread will be blocked until the pervious operations are processed by the video memory manager.


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
<a href="display.d3dddicb_updategpuvirtualaddress">D3DDDICB_UPDATEGPUVIRTUALADDRESS</a>
</dt>
<dt>
<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_reservegpuvirtualaddresscb.md">pfnReserveGpuVirtualAddressCb</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20PFND3DDDI_UPDATEGPUVIRTUALADDRESSCB callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

