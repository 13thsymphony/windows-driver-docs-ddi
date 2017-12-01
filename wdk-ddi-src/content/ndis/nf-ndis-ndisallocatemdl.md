---
UID: NF.ndis.NdisAllocateMdl
title: NdisAllocateMdl
author: windows-driver-content
description: The NdisAllocateMdl function allocates an MDL that describes the memory buffer at the specified virtual address.
old-location: netvista\ndisallocatemdl.htm
old-project: netvista
ms.assetid: 4863fe31-2c89-47af-99ed-02055e67621d
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: NdisAllocateMdl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisAllocateMdl
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_NetBuffer_Function, NdisAllocateMdl
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# NdisAllocateMdl function



## -description
<p>The 
  <b>NdisAllocateMdl</b> function allocates an MDL that describes the memory buffer at the specified virtual
  address.</p>


## -syntax

````
PMDL NdisAllocateMdl(
  _In_ NDIS_HANDLE NdisHandle,
  _In_ PVOID       VirtualAddress,
  _In_ UINT        Length
);
````


## -parameters
<dl>

### -param <i>NdisHandle</i> [in]

<dd>
<p>An NDIS handle that was obtained during caller initialization. For more information, see 
     <a href="NULL">Obtaining Pool Handles</a>.</p>
</dd>

### -param <i>VirtualAddress</i> [in]

<dd>
<p>A pointer to the base virtual address of the buffer that the MDL is to describe.</p>
<div class="alert"><b>Important</b>  <p class="note">The <b>VirtualAddress</b> parameter for <b>NdisAllocateMdl</b> only accepts memory from the nonpaged pool. In other words, it requires memory from <a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>*(NonPagedNx), <a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">NdisAllocateMemoryWithTagPriority</a>, or <a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a>. In particular, it should <b>not</b> be used with memory from the stack, paged pool, driver global data, or other memory regions.</p>
<p class="note">If a driver needs to build an MDL for one of these non-nonpaged pool regions, it should use the appropriate kernel APIs for that type of memory, such as <a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a> combined with <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages.</a>
</p>
</div>
<div> </div>
</dd>

### -param <i>Length</i> [in]

<dd>
<p>The size, in bytes, of the memory buffer.</p>
</dd>
</dl>

## -returns
<p><b>NdisAllocateMdl</b> returns a pointer to the allocated MDL. If the allocation fails, the return value
     is <b>NULL</b>.</p>

## -remarks
<p>All MDLs that are allocated by calling 
    <b>NdisAllocateMdl</b> must be freed by calling the 
    <a href="..\ndis\nf-ndis-ndisfreemdl.md">NdisFreeMdl</a> function.</p>

<p><b>NdisAllocateMdl</b> allocates memory and builds the MDL in one step. This process is different from 
    <a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>, which only allocates memory for
    the MDL, meaning the caller must build the MDL by calling either 
    <a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a> or 
    <a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages.</a>
</p>

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
<p>Supported in NDIS 6.0 and later.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
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
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="devtest.ndis_irql_netbuffer_function">Irql_NetBuffer_Function</a>, <a href="..\ndis\nf-ndis-ndisallocatemdl.md">NdisAllocateMdl</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioallocatemdl.md">IoAllocateMdl</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmbuildmdlfornonpagedpool.md">MmBuildMdlForNonPagedPool</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-mmprobeandlockpages.md">MmProbeAndLockPages</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreemdl.md">NdisFreeMdl</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exallocatepool.md">ExAllocatePool</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocatememorywithtagpriority.md">NdisAllocateMemoryWithTagPriority</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndismallocatesharedmemory.md">NdisMAllocateSharedMemory</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisAllocateMdl function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
