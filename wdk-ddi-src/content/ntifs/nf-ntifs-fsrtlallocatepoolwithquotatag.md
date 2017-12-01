---
UID: NF.ntifs.FsRtlAllocatePoolWithQuotaTag
title: FsRtlAllocatePoolWithQuotaTag
author: windows-driver-content
description: The FsRtlAllocatePoolWithQuotaTag routine allocates pool memory, charging quota against the current process.
old-location: ifsk\fsrtlallocatepoolwithquotatag.htm
old-project: ifsk
ms.assetid: 241525fd-c21b-4c24-91a0-6a79df4faea7
ms.author: windowsdriverdev
ms.date: 11/14/2017
ms.keywords: FsRtlAllocatePoolWithQuotaTag
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlAllocatePoolWithQuotaTag
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
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.iface: 
---

# FsRtlAllocatePoolWithQuotaTag function



## -description
<p>The <b>FsRtlAllocatePoolWithQuotaTag</b> routine allocates pool memory, charging quota against the current process. </p>


## -syntax

````
PVOID FsRtlAllocatePoolWithQuotaTag(
  _In_ POOL_TYPE PoolType,
  _In_ ULONG     NumberOfBytes,
  _In_ ULONG     Tag
);
````


## -parameters
<dl>

### -param <i>PoolType</i> [in]

<dd>
<p>Type of pool to allocate. One of the following:</p>
<p>
<ul>
<li><b>NonPagedPool</b></li>
<li><b>PagedPool</b></li>
<li><b>NonPagedPoolCacheAligned</b></li>
<li><b>PagedPoolCacheAligned</b></li>
</ul>
</p>
<div class="alert"><b>Note</b>    The <b>NonPagedPoolMustSucceed</b> and <b>NonPagedPoolCacheAlignedMustS</b> pool types are obsolete and should no longer be used.</div>
<div> </div>
</dd>

### -param <i>NumberOfBytes</i> [in]

<dd>
<p>Number of bytes to allocate.</p>
</dd>

### -param <i>Tag</i> [in]

<dd>
<p>Specifies the pool tag for the allocated memory. Drivers normally specify the pool tag as a string of one to four 7-bit ASCII characters, delimited by single quotation marks (for example, 'abcd'). This parameter is required and cannot be zero. </p>
</dd>
</dl>

## -returns
<p><b>FsRtlAllocatePoolWithQuotaTag</b> returns a non-NULL pointer to the newly allocated pool.</p>

## -remarks
<p>If a pool allocation failure occurs, <b>FsRtlAllocatePoolWithQuotaTag</b> raises a STATUS_INSUFFICIENT_RESOURCES exception. To gain control if this pool allocation failure occurs, the driver should wrap the call to <b>FsRtlAllocatePoolWithQuotaTag</b> in a <b>try-except</b> or <b>try-finally</b> statement.</p>

<p>The system associates the pool tag specified by the <i>Tag</i> parameter with the allocated buffer. Programming tools, such as the Windows Debugger (WinDbg), can display the pool tag associated with each allocated buffer. The value of the pool tag is normally displayed in reversed order. For example, if a caller passes 'Fred' as the value of the <i>Tag</i> parameter, this value would appear as 'derF' if pool is dumped or when tracking pool usage in the debugger. </p>

<p>For more information about memory management, see <a href="https://msdn.microsoft.com/e030a37c-26ab-4177-9980-4336928975e1">Memory Management</a>. </p>

<p>Callers of <b>FsRtlAllocatePoolWithQuotaTag</b> must be running at IRQL &lt;= DISPATCH_LEVEL. A caller at DISPATCH_LEVEL must specify a <b>NonPaged</b><i>XxxPoolType</i>. Otherwise, the caller must be running at IRQL &lt; DISPATCH_LEVEL.</p>

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
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
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
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exallocatepoolwithquotatag.md">ExAllocatePoolWithQuotaTag</a>
</dt>
<dt>
<a href="..\ntddk\nf-ntddk-exfreepool.md">ExFreePool</a>
</dt>
<dt>
<a href="ifsk.fsrtlallocatepoolwithquota">FsRtlAllocatePoolWithQuota</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAllocatePoolWithQuotaTag routine%20 RELEASE:%20(11/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
