---
UID: NF.wdm.MmAllocateMdlForIoSpace
title: MmAllocateMdlForIoSpace
author: windows-driver-content
description: The MmAllocateMdlForIoSpace routine allocates an MDL and initializes this MDL to describe a set of physical address ranges in I/O address space.
old-location: kernel\mmallocatemdlforiospace.htm
old-project: kernel
ms.assetid: 198ECC2A-1AC0-44FA-8E5C-84F1C8BEE246
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: MmAllocateMdlForIoSpace
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmAllocateMdlForIoSpace
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# MmAllocateMdlForIoSpace function



## -description
<p>The <b>MmAllocateMdlForIoSpace</b> routine allocates an <a href="..\wdm\ns-wdm--mdl.md">MDL</a> and initializes this MDL to describe a set of physical address ranges in I/O address space.</p>


## -syntax

````
NTSTATUS MmAllocateMdlForIoSpace(
  _In_  PMM_PHYSICAL_ADDRESS_LIST PhysicalAddressList,
  _In_  SIZE_T                    NumberOfEntries,
  _Out_ PMDL                      *NewMdl
);
````


## -parameters
<dl>

### -param PhysicalAddressList [in]

<dd>
<p>A pointer to an array of <a href="..\wdm\ns-wdm--mm-physical-address-list.md">MM_PHYSICAL_ADDRESS_LIST</a> structures that describe the physical address ranges to include in the allocated MDL.</p>
</dd>

### -param NumberOfEntries [in]

<dd>
<p>The number of elements in the <b>MM_PHYSICAL_ADDRESS_LIST</b> array pointed to by <i>PhysicalAddressList</i>.</p>
</dd>

### -param NewMdl [out]

<dd>
<p>A pointer to a location to which the routine writes a pointer to the newly allocated MDL.</p>
</dd>
</dl>

## -returns
<p><b>MmAllocateMdlForIoSpace</b> returns STATUS_SUCCESS if it is successful. Possible error return values include the following status codes.</p><dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl><p>A physical address is not aligned to a page boundary; or a physical address range is not a multiple of the page size; or a physical address range is used by the operating system for RAM and is not available for use as I/O space.</p><dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl><p>Insufficient system resources are available to perform the requested operation.</p>

<p> </p>

<p>Do not assume that the preceding list of error return codes is exhaustive. The routine might return error codes that do not appear in the list.</p>

## -remarks
<p>This routine accepts, as an input parameter, an array of <b>MM_PHYSICAL_ADDRESS_LIST</b> structures that describe a set of physical address ranges in I/O address space, and allocates an MDL that describes these ranges. Consecutive physical address ranges in the array are not required to be contiguous.</p>

<p>The physical address ranges in the <i>PhysicalAddressList</i> array must satisfy the following conditions:</p>

<p>The caller is responsible for freeing the allocated MDL when it is no longer needed. To free the MDL, call the <a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a> routine. For more information about MDLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565421">Using MDLs</a>.</p>

<p>The MDL that is created by <b>MmAllocateMdlForIoSpace</b> is not mapped to virtual memory, but can be supplied to a routine such as <a href="kernel.maptransferex">MapTransferEx</a> to initiate a DMA transfer to or from the physical memory ranges described by the MDL. To map this MDL to a contiguous range of virtual addresses so that it can be accessed by the processor, call the <a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a> routine.</p>

<p>Only ranges of the physical address space that are not reserved by the operating system for use as memory are available to drivers for use as I/O address space. Drivers use I/O address space to access memory-mapped hardware resources such as device registers. When a driver starts, it might receive one or more physical address ranges as translated hardware resources. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff554399">Mapping Bus-Relative Addresses to Virtual Addresses</a>.</p>

<p>In some processor architectures, such as the x86, devices can be either memory-mapped or mapped to port addresses in a special  I/O address space that is dedicated to devices and is separate from the memory address space. Drivers can use <b>MmAllocateMdlForIoSpace</b> to allocate MDLs only for memory-mapped devices.</p>

<p>The following code example shows how to construct an array of <a href="..\wdm\ns-wdm--mm-physical-address-list.md">MM_PHYSICAL_ADDRESS_LIST</a> structures that describe the physical address ranges to include in the allocated MDL.</p>

<p>In this example, the starting physical address is specified by the <code>BasePhysicalAddress</code> variable. The number of bytes in each physical address range is specified by the <code>ChunkSize</code> variable. The byte offset from the start of one physical range to the start of the next is specified by the <code>Stride</code> variable. <code>BasePhysicalAddress</code> must be aligned to a page boundary in memory, and <code>ChunkSize</code> and <code>Stride</code> must be multiples of the page size.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Available starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>DLL</p>
</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-iofreemdl.md">IoFreeMdl</a>
</dt>
<dt>
<a href="kernel.maptransferex">MapTransferEx</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--mdl.md">MDL</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmmaplockedpagesspecifycache.md">MmMapLockedPagesSpecifyCache</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--mm-physical-address-list.md">MM_PHYSICAL_ADDRESS_LIST</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocateMdlForIoSpace routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
