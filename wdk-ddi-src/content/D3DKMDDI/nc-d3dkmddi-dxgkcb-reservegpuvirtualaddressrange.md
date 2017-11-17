---
UID: NC.d3dkmddi.DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
title: DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE
author: windows-driver-content
description: DxgkCbReserveGpuVirtualAddressRange allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process.
old-location: display\dxgkcbreservegpuvirtualaddressrange.htm
ms.assetid: 26A827F1-1094-4A7D-9C63-758925EE6273
ms.author: windowsdriverdev
ms.date: 10/25/2017
ms.topic: callback
ms.prod: windows-hardware
ms.technology: display
req.header: d3dkmddi.h
req.include-header: Dispmprt.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DxgkCbReserveGpuVirtualAddressRange
req.alt-loc: dispmprt.h,d3dkmddi.h
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
ms.keywords: DD_MULTISAMPLEQUALITYLEVELSDATA, DD_MULTISAMPLEQUALITYLEVELSDATA
req.iface: 
---

# DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback



## -description
<p><b>DxgkCbReserveGpuVirtualAddressRange</b> allows the kernel mode driver to reserve a graphics processing unit (GPU) virtual address range during creation of a process. Reserving the GPU virtual address range is only possible during process creation (i.e. within the call to <a href="https://msdn.microsoft.com/E5AAEEB1-C29E-4AA7-9F8E-2C2DCFADED81">DxgkDdiCreateProcess</a>) and is invalid at any other time.</p>
<p>Reservation is possible on both regular process as well as the system process where the system device and context lives.
</p>
<p>The first entry in the root page table (page table entry index 0) will always be initialized as invalid by the video memory manager and the driver reservations will start from page table entry  index 1. Driver reservation must always be an exact multiple of virtual address space, covered by leaf page table, as the specific page table entry can’t be shared between the video memory manager and the kernel mode driver. Page table entries reserved by the driver will be initialized as <i>invalid</i> by the video memory manager and may be overwritten by the driver to reference an internally allocated page table managed by the driver. The video memory manager will update the reserved page table entries as invalid every time the corresponding page table becomes resident.

  </p>


## -prototype

````
DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE DxgkCbReserveGpuVirtualAddressRange;

NTSTATUS APIENTRY CALLBACK* DxgkCbReserveGpuVirtualAddressRange(
  _In_    const HANDLE                                  hAdapter,
  _Inout_       DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE *pArgs
)
{ ... }
````


## -parameters
<dl>

### -param <i>hAdapter</i> [in]

<dd>
<p>A handle to the display adapter.</p>
</dd>

### -param <i>pArgs</i> [in, out]

<dd>
<p>The <a href="https://msdn.microsoft.com/library/windows/hardware/dn906819">DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</a> structure that describes the operation.</p>
</dd>
</dl>

## -returns
<p>
      Returns <b>STATUS_SUCCESS</b> if it succeeds. Otherwise, it returns one of the error codes defined in <b>Ntstatus.h</b>.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Dispmprt.h (include Dispmprt.h); </dt>
<dt>D3dkmddi.h (include D3dkmddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/E5AAEEB1-C29E-4AA7-9F8E-2C2DCFADED81">DxgkDdiCreateProcess</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/dn906819">DXGKARGCB_RESERVEGPUVIRTUALADDRESSRANGE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKCB_RESERVEGPUVIRTUALADDRESSRANGE callback function%20 RELEASE:%20(10/25/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
