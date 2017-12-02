---
UID: NF.fltkernel.FltFastIoPrepareMdlWrite
title: FltFastIoPrepareMdlWrite
author: windows-driver-content
description: The FltFastIoPrepareMdlWrite routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.
old-location: ifsk\fltfastiopreparemdlwrite.htm
old-project: ifsk
ms.assetid: 7C48D179-35FA-44E1-B959-BD857AAA28E1
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FltFastIoPrepareMdlWrite
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlPrepareMdlWriteDev
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
req.irql: <= APC_LEVEL
req.iface: 
---

# FltFastIoPrepareMdlWrite function



## -description
<p>The <b>FltFastIoPrepareMdlWrite</b> routine returns a linked list of memory descriptor lists (MDLs) that point to the specified range of cached file data to write data directly to the cache.</p>


## -syntax

````
BOOLEAN FsRtlPrepareMdlWriteDev(
        PFLT_INSTANCE    InitiatingInstance,
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  ULONG            LockKey,
  _Out_ PMDL             *MdlChain,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````


## -parameters
<dl>

### -param InitiatingInstance 

<dd>
<p>Opaque instance pointer for the caller. This parameter is required and cannot be <b>NULL</b>. </p>
</dd>

### -param FileObject [in]

<dd>
<p>A pointer to the file object.</p>
</dd>

### -param FileOffset [in]

<dd>
<p>A pointer to a value that specifies the starting byte offset within the cache that holds the data.</p>
</dd>

### -param Length [in]

<dd>
<p>The length in bytes of the data to read from the cache.</p>
</dd>

### -param LockKey [in]

<dd>
<p>A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked non-exclusively, the value in this parameter must be the key for that nonexclusive lock. The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.</p>
</dd>

### -param MdlChain [out]

<dd>
<p>On output, a pointer to a linked list of memory descriptor lists (MDLs) that point to the byte range within the cached data.</p>
</dd>

### -param IoStatus [out]

<dd>
<p>A pointer to an <a href="..\wdm\ns-wdm--io-status-block.md">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to STATUS_SUCCESS. Otherwise, it is set to an appropriate NTSTATUS error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.</p>
</dd>
</dl>

## -returns
<p>The <b>FltFastIoPrepareMdlWrite</b> routine returns <b>TRUE</b> if the operation succeeds and <b>FALSE</b> if the operation fails.</p>

## -remarks
<p><b>FltFastIoPrepareMdlWrite</b> is similar to <a href="ifsk.fsrtlcopywrite">FsRtlCopyWrite</a>, except that <b>FltFastIoPrepareMdlWrite</b> does not copy data to the cache. Instead, the physical pages that the caller will overwrite are locked in memory, and <b>FltFastIoPrepareMdlWrite</b> returns one or more memory descriptor lists (MDLs) that point to the specified byte range. The locked pages remain locked until the caller calls <a href="..\fltkernel\nf-fltkernel-fltfastiomdlwritecomplete.md">FltFastIoMdlWriteComplete</a>. Thus each call to <b>FltFastIoPrepareMdlWrite</b> must be followed by a call to <b>FltFastIoMdlWriteComplete</b>.</p>

<p>The pages that the MDLs point to are locked in memory, but are not mapped in system space. The caller can perform this mapping by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>.</p>

<p>Even if the call to <b>FltFastIoPrepareMdlWrite</b> fails, one or more MDLs might have been allocated. The caller can examine the value of <i>IoStatus.Information</i> to determine if this has occurred. If it has, the caller must call <a href="..\fltkernel\nf-fltkernel-fltfastiomdlwritecomplete.md">FltFastIoMdlWriteComplete</a> to free the allocated MDLs.</p>

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
<dt>Fltkernel.h (include Ntifs.h)</dt>
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
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.fsrtlcopywrite">FsRtlCopyWrite</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfastiomdlwritecomplete.md">FltFastIoMdlWriteComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltFastIoPrepareMdlWrite routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
