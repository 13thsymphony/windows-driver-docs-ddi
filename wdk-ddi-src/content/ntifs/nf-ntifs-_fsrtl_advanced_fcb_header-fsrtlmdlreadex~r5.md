---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlMdlReadEx~r5
title: FsRtlMdlReadEx function
author: windows-driver-content
description: The FsRtlMdlReadEx routine performs a fast cached MDL read. If the requested data is not cached, the routine reverts to an IRP based MDL read operation.
old-location: ifsk\fsrtlmdlreadex.htm
old-project: ifsk
ms.assetid: E1F16454-C8E6-4291-83BB-F4CF18F6DF10
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FsRtlMdlReadEx
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlMdlReadEx
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
req.irql: PASSIVE_LEVEL
---

# FsRtlMdlReadEx function



## -description
The <b>FsRtlMdlReadEx</b> routine performs a fast cached MDL read.  If the requested data is not cached, the routine reverts to an IRP based MDL read operation.



## -syntax

````
NTSTATUS FsRtlMdlReadEx(
  _In_  PFILE_OBJECT     FileObject,
  _In_  PLARGE_INTEGER   FileOffset,
  _In_  ULONG            Length,
  _In_  ULONG            LockKey,
  _Out_ PMDL             *MdlChain,
  _Out_ PIO_STATUS_BLOCK IoStatus
);
````


## -parameters

### -param FileObject [in]

A pointer to the file object.


### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file that holds the data.


### -param Length [in]

The length in bytes of the data to read from the cache.


### -param LockKey [in]

A value that is associated with the byte range to lock. If the range to lock overlaps another range that is already locked with a nonexclusive lock, or if the range to read is a subrange of another range that is already locked nonexclusively, the value in this parameter must be the key for that nonexclusive lock The lock must be held by the parent process of the calling thread. Otherwise, this parameter has no effect.


### -param MdlChain [out]

On output, a pointer to a linked list of memory descriptor lists (MDLs).


### -param IoStatus [out]

A pointer to an <a href="kernel.io_status_block">IO_STATUS_BLOCK</a> structure that, on output, contains the status of the transfer. If the operation succeeds, <i>IoStatus.Status</i> is set to <b>STATUS_SUCCESS</b>. Otherwise, it is set to an appropriate <b>NTSTATUS</b> error code. <i>IoStatus.Information</i> is set to the actual number of bytes that the routine successfully locked.


## -returns
<b>FsRtlMdlReadEx</b> returns <b>STATUS_SUCCESS</b> or an appropriate <b>NTSTATUS</b> value, such as one of the following: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The IRP for an the IRP based read could not be allocated.

 


## -remarks
If fast I/O is available from the file system, the <b>FsRtlMdlReadEx</b> routine will bypass the usual IRP read mechanism and return a linked list of memory descriptor lists (MDL) that the caller can use to directly access the cached file data. This operation does not copy or buffer data and therefore is much faster than a normal read. If fast I/O is not enabled, <b>FsRtlMdlReadEx</b> will generate a synchronous IRP based MDL read and return the MDLs from the request.

The pages described by the MDLs are locked in memory, but not mapped in system space. The caller can perform this mapping by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>. 

Similar to <a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>, the <b>FsRtlMdlReadEx</b> routine locks the pages that contain the cached file data to prevent the system from swapping these pages to the page file. The pages remain locked in memory until the caller invokes the <b>CcMdlReadComplete</b> routine.


## -requirements
<table>
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
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include Ntifs.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
DLL

</th>
<td width="70%">
<dl>
<dt>NtosKrnl.exe</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539159">CcMdlRead</a>
</dt>
<dt>
<a href="ifsk.ccmdlreadcomplete">CcMdlReadComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff554559">MmGetSystemAddressForMdlSafe</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlMdlReadEx routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

