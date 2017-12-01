---
UID: NF.wdm.ExAllocatePool
title: ExAllocatePool
author: windows-driver-content
description: The ExAllocatePool routine is obsolete, and is exported only for existing binaries. Use ExAllocatePoolWithTag instead.ExAllocatePool allocates pool memory of the specified type and returns a pointer to the allocated block.
old-location: kernel\exallocatepool.htm
old-project: kernel
ms.assetid: b5b88a14-3d60-45bf-8340-b78175a55e01
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: ExAllocatePool
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete. This routine is exported only for existing binaries. Use ExAllocatePoolWithTag instead.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ExAllocatePool
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs, SpNoWait, StorPortStartIo
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# ExAllocatePool function



## -description
<p>The <b>ExAllocatePool</b> routine is <u>obsolete</u>, and is exported only for existing binaries. Use <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> instead.</p>
<p><b>ExAllocatePool</b> allocates pool memory of the specified type and returns a pointer to the allocated block.</p>


## -syntax

````
PVOID ExAllocatePool(
  _In_ POOL_TYPE PoolType,
  _In_ SIZE_T    NumberOfBytes
);
````


## -parameters
<dl>

### -param <i>PoolType</i> [in]

<dd>
<p>Specifies the type of pool memory to allocate. For a description of the available pool memory types, see <a href="..\wdm\ne-wdm--pool-type.md">POOL_TYPE</a>.</p>
<p>You can modify <i>PoolType</i> by using a bitwise OR with the POOL_COLD_ALLOCATION flag as a hint to the kernel to allocate the memory from pages that are likely to be paged out quickly. To reduce the amount of resident pool memory as much as possible, you should not reference these allocations frequently. The POOL_COLD_ALLOCATION flag is only advisory and is available for Windows XP and later versions of the Windows operating system.</p>
</dd>

### -param <i>NumberOfBytes</i> [in]

<dd>
<p>Specifies the number of bytes to allocate. </p>
</dd>
</dl>

## -returns
<p><b>ExAllocatePool</b> returns <b>NULL</b> if there is insufficient memory in the free pool to satisfy the request. Otherwise the routine returns a pointer to the allocated memory.</p>

## -remarks
<p>This routine is used for the general pool allocation of memory.</p>

<p>If <i>NumberOfBytes</i> is PAGE_SIZE or greater, a page-aligned buffer is allocated. Memory allocations of PAGE_SIZE or less do not cross page boundaries. Memory allocations of less than PAGE_SIZE are not necessarily page-aligned but are aligned to 8-byte boundaries in 32-bit systems and to 16-byte boundaries in 64-bit systems.</p>

<p>A successful allocation requesting <i>NumberOfBytes</i> &lt; PAGE_SIZE of nonpaged pool gives the caller exactly the number of requested bytes of memory. If an allocation request for <i>NumberOfBytes</i> &gt; PAGE_SIZE succeeds and <i>NumberOfBytes</i> is not an exact multiple of PAGE_SIZE, the last page in the allocation contains bytes that are not part of the caller's allocation. If possible, the pool allocator uses these bytes. To avoid corrupting data that belongs to other kernel-mode components, drivers must access only storage addresses that they have explicitly allocated.</p>

<p>If <b>ExAllocatePool</b> returns <b>NULL</b>, the caller should return the NTSTATUS value STATUS_INSUFFICIENT_RESOURCES or should delay processing to another point in time.</p>

<p>Callers of <b>ExAllocatePool</b> must be executing at IRQL &lt;= DISPATCH_LEVEL. A caller executing at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>Xxx</i> value for <i>PoolType</i>. A caller executing at IRQL &lt;= APC_LEVEL can specify any <b>POOL_TYPE</b> value, but the IRQL and environment must also be considered for determining the page type.</p>

<p>The system automatically sets certain standard event objects when the amount of pool (paged or nonpaged) is high or low. Drivers can wait for these events to tune their pool usage. For more information, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff563847">Standard Event Objects</a>.</p>

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
<p>Obsolete. This routine is exported only for existing binaries. Use <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> instead.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
<p>&lt;= DISPATCH_LEVEL (see Remarks section)</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>, <a href="devtest.storport_spnowait">SpNoWait</a>, <a href="devtest.storport_storportstartio">StorPortStartIo</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm--pool-type.md">POOL_TYPE</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExAllocatePool routine%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
