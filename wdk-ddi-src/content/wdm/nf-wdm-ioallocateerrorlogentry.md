---
UID: NF.wdm.IoAllocateErrorLogEntry
title: IoAllocateErrorLogEntry function
author: windows-driver-content
description: The IoAllocateErrorLogEntry routine allocates an error log entry, and returns a pointer to the packet that the caller uses to supply information about an I/O error.
old-location: kernel\ioallocateerrorlogentry.htm
old-project: kernel
ms.assetid: 07fc3ae1-325a-4e50-a83d-9e70a8d63aaa
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IoAllocateErrorLogEntry
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 2000 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoAllocateErrorLogEntry
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
req.product: Windows 10 or later.
---

# IoAllocateErrorLogEntry function



## -description
The <b>IoAllocateErrorLogEntry</b> routine allocates an error log entry, and returns a pointer to the packet that the caller uses to supply information about an I/O error.


## -syntax

````
PVOID IoAllocateErrorLogEntry(
  _In_ PVOID IoObject,
  _In_ UCHAR EntrySize
);
````


## -parameters

### -param IoObject [in]

Pointer to a device object representing the device on which an I/O error occurred, or to a driver object representing the driver that found an error.

### -param EntrySize [in]

Specifies the size, in bytes, of the error log entry to be allocated. This value cannot exceed ERROR_LOG_MAXIMUM_SIZE. 
<div class="alert"><b>Warning</b>  <i>EntrySize</i> is a UCHAR value. If you specify a larger value, the compiler will silently truncate that value to a (wrong) UCHAR. </div>
<div> </div>

## -returns
<b>IoAllocateErrorLogEntry</b> returns a pointer to the error log entry, or <b>NULL</b> if a log entry could not be allocated.

## -remarks
The driver must first fill in the packet with information about the error, then call <a href="kernel.iowriteerrorlogentry">IoWriteErrorLogEntry</a> to post the entry to the error log. The error log entry buffer is automatically freed once the log entry is recorded. Entry buffers that are not going to be written to the log can be freed by using <a href="kernel.iofreeerrorlogentry">IoFreeErrorLogEntry</a>.

An error log entry consists of a variable-length <a href="kernel.io_error_log_packet">IO_ERROR_LOG_PACKET</a> structure, possibly followed by one or more zero-counted Unicode strings. The Event Viewer inserts these strings into the error message it displays for the entry. <b>IO_ERROR_LOG_PACKET</b> contains one variable-length member, the <b>DumpData</b> member. Thus, the value for <i>EntrySize</i> must be <b>sizeof</b>(<b>IO_ERROR_LOG_PACKET</b>) + size of the <b>DumpData</b> member + combined size of any driver-supplied insertion strings.

Drivers should check that the value for <i>EntrySize</i> is less than ERROR_LOG_MAXIMUM_SIZE before calling <b>IoAllocateErrorLogEntry</b>. Since <i>EntrySize</i>  is declared as a UCHAR, and the compiler will silently truncate any value too big to fit into a UCHAR, the routine itself cannot reliably detect if the passed value is too large.

Drivers must not treat <b>IoAllocateErrorLogEntry</b> returning <b>NULL</b> as a fatal error. The driver must continue to function normally, regardless of whether it can log errors.

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
Available in Windows 2000 and later versions of Windows.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
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
&lt;= DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.io_error_log_packet">IO_ERROR_LOG_PACKET</a>
</dt>
<dt>
<a href="kernel.iofreeerrorlogentry">IoFreeErrorLogEntry</a>
</dt>
<dt>
<a href="kernel.iowriteerrorlogentry">IoWriteErrorLogEntry</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoAllocateErrorLogEntry routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
