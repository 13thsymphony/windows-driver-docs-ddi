---
UID: NF.ntddk.MmAllocateContiguousMemorySpecifyCache
title: MmAllocateContiguousMemorySpecifyCache
author: windows-driver-content
description: The MmAllocateContiguousMemorySpecifyCache routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.
old-location: kernel\mmallocatecontiguousmemoryspecifycache.htm
old-project: kernel
ms.assetid: e35544ed-d113-476e-85a8-6b3f613c1dc2
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: MmAllocateContiguousMemorySpecifyCache
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: MmAllocateContiguousMemorySpecifyCache
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
---

# MmAllocateContiguousMemorySpecifyCache function



## -description
<p>The <b>MmAllocateContiguousMemorySpecifyCache</b> routine allocates a range of contiguous, nonpaged physical memory and maps it to the system address space.</p>


## -syntax

````
PVOID MmAllocateContiguousMemorySpecifyCache(
  _In_     SIZE_T              NumberOfBytes,
  _In_     PHYSICAL_ADDRESS    LowestAcceptableAddress,
  _In_     PHYSICAL_ADDRESS    HighestAcceptableAddress,
  _In_opt_ PHYSICAL_ADDRESS    BoundaryAddressMultiple,
  _In_     MEMORY_CACHING_TYPE CacheType
);
````


## -parameters
<dl>

### -param NumberOfBytes [in]

<dd>
<p>The size, in bytes, of the block of contiguous memory to allocate. For more information, see Remarks.</p>
</dd>

### -param LowestAcceptableAddress [in]

<dd>
<p>The lowest valid physical address the caller can use. For example, if a device can address only locations above the first 8 megabytes of the processor's physical memory address range, the driver for this device  should set <i>LowestAcceptableAddress</i> to 0x0000000000800000.</p>
</dd>

### -param HighestAcceptableAddress [in]

<dd>
<p>The highest valid physical address the caller can use. For example, if a device can address only locations in the first 16 megabytes of the processor's physical memory address range, the driver for this device should set <i>HighestAcceptableAddress</i> to 0x0000000000FFFFFF.</p>
</dd>

### -param BoundaryAddressMultiple [in, optional]

<dd>
<p>The physical address multiple that the allocated buffer must not cross. A physical address multiple must always be a power of two. This parameter is optional and can be specified as zero to indicate that the device has no special memory boundary restrictions. For more information, see Remarks.</p>
</dd>

### -param CacheType [in]

<dd>
<p>Specifies a <a href="..\wdm\ne-wdm--memory-caching-type.md">MEMORY_CACHING_TYPE</a> value, which indicates the type of caching allowed for the requested memory.</p>
</dd>
</dl>

## -returns
<p><b>MmAllocateContiguousMemorySpecifyCache</b> returns the base virtual address for the allocated memory. If the system is unable to allocate the requested buffer, the routine returns <b>NULL</b>.</p>

## -remarks
<p><b>MmAllocateContiguousMemorySpecifyCache</b> allocates a block of nonpaged memory that is contiguous in physical address space. The routine maps this block to a contiguous block of virtual memory in the system address space and returns the virtual address of the base of this block. The routine aligns the starting address of a contiguous memory allocation to a memory page boundary.</p>

<p>Drivers must not access memory beyond the requested allocation size. For example, developers should not assume that their drivers can safely use memory between the end of their requested allocation and the next page boundary.</p>

<p>Because contiguous physical memory is usually in short supply, it should be used sparingly and only when necessary. A driver that must use contiguous memory should allocate this memory during driver initialization because physical memory is likely to become fragmented over time as the operating system allocates and frees memory. Typically, a driver calls <b>MmAllocateContiguousMemorySpecifyCache</b> from its <a href="..\wdm\nc-wdm-driver-initialize.md">DriverEntry</a> routine to allocate an internal buffer for long-term use, and frees the buffer just before the driver is unloaded.</p>

<p>Memory allocated by <b>MmAllocateContiguousMemorySpecifyCache</b> must be freed when the memory is no longer needed. Call the <a href="..\ntddk\nf-ntddk-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a> routine to free memory that is allocated by <b>MmAllocateContiguousMemorySpecifyCache</b>.</p>

<p>If you specify a nonzero value for the <i>BoundaryAddressMultiple</i> parameter, the physical address range of the allocated memory block will not cross an address boundary that is an integer multiple of this value. A driver should set this parameter to zero unless a nonzero value is required to work around a hardware limitation. For example, if a device cannot transfer data across 16-megabyte physical boundaries, the driver should specify a value of 0x1000000 for this parameter to ensure that the addresses that the device sees do not wrap around at a 16-megabyte boundary.</p>

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
<p>Available starting with Windows 2000.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntddk.h (include Ntddk.h)</dt>
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
<a href="..\ntddk\nf-ntddk-mmallocatecontiguousmemory.md">MmAllocateContiguousMemory</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-mmfreecontiguousmemory.md">MmFreeContiguousMemory</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20MmAllocateContiguousMemorySpecifyCache routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
