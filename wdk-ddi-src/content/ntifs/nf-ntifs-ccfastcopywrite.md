---
UID: NF.ntifs.CcFastCopyWrite
title: CcFastCopyWrite function
author: windows-driver-content
description: The CcFastCopyWrite routine performs a fast copy write from a buffer in memory to a cached file.
old-location: ifsk\ccfastcopywrite.htm
old-project: ifsk
ms.assetid: 414d0b36-d7c2-4a01-8ceb-3817a11c422c
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: CcFastCopyWrite
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
req.alt-api: CcFastCopyWrite
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
req.irql: 
---

# CcFastCopyWrite function



## -description
The <b>CcFastCopyWrite</b> routine performs a fast copy write from a buffer in memory to a cached file.


## -syntax

````
VOID CcFastCopyWrite(
  _In_ PFILE_OBJECT FileObject,
  _In_ ULONG        FileOffset,
  _In_ ULONG        Length,
  _In_ PVOID        Buffer
);
````


## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file to which the data is to be written.

### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file.

### -param Length [in]

Length in bytes of the data to be written.

### -param Buffer [in]

Pointer to the buffer from which the data is to be copied.

## -returns
None

## -remarks
<b>CcFastCopyWrite</b> is a faster version of <a href="ifsk.cccopywrite">CcCopyWrite</a>. It differs from <b>CcCopyWrite</b> in the following respects:

<i>FileOffset</i> is a ULONG, not a PLARGE_INTEGER.

There is no <i>Wait</i> parameter. The caller must be able to enter a wait state until all the data has been copied.

<b>CcFastCopyWrite</b> does not return a BOOLEAN to indicate whether the write operation was successful.

If the required pages of the cached file are already resident in memory, the data is copied immediately and no blocking occurs. If any needed pages are not resident, the caller is put in a wait state until all required pages have been made resident and the data can be copied.

If any failure occurs, <b>CcFastCopyWrite</b> raises a status exception for that particular failure. For example, if a pool allocation failure occurs, <b>CcFastCopyWrite</b> raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, <b>CcFastCopyWrite</b> raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to <b>CcFastCopyWrite</b> in a <b>try-except</b> or <b>try-finally</b> statement.

To cache a file, use <a href="ifsk.ccinitializecachemap">CcInitializeCacheMap</a>.

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
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.cccopywrite">CcCopyWrite</a>
</dt>
<dt>
<a href="ifsk.ccinitializecachemap">CcInitializeCacheMap</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcFastCopyWrite routine%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
