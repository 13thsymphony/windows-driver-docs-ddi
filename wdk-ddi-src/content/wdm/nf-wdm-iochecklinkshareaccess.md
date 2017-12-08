---
UID: NF.wdm.IoCheckLinkShareAccess
title: IoCheckLinkShareAccess function
author: windows-driver-content
description: The IoCheckLinkShareAccess routine is called by file system drivers (FSDs) or other highest-level drivers to check whether link shared access to a file object is permitted.
old-location: kernel\iochecklinkshareaccess.htm
old-project: kernel
ms.assetid: 1C34237E-D4AF-4F12-9FF2-9382BADCC9D3
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IoCheckLinkShareAccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoCheckLinkShareAccess
req.alt-loc: ntoskrnl.lib,ntoskrnl.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# IoCheckLinkShareAccess function



## -description
The <b>IoCheckLinkShareAccess</b> routine is called by file system drivers (FSDs) or other highest-level drivers to check whether link shared access to a file object is permitted.


## -syntax

````
NTSTATUS IoCheckLinkShareAccess(
  _In_        ACCESS_MASK        DesiredAccess,
  _In_        ULONG              DesiredShareAccess,
  _Inout_     PFILE_OBJECT       FileObject,
  _Inout_     PSHARE_ACCESS      ShareAccess,
  _Inout_opt_ PLINK_SHARE_ACCESS LinkShareAccess,
  _In_        ULONG              IoShareAccessFlags
);
````


## -parameters

### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that indicates the desired type of access to the given file object.

### -param DesiredShareAccess [in]

Specifies the desired type of shared access to the file object for the current open request. The value of this parameter is usually the same as the <i>ShareAccess</i> parameter that is passed to the file system or highest-level driver by the I/O manager when the open request was made. This value can be zero, or any combination of the following:
<dl>
<dd>
FILE_SHARE_READ
</dd>
<dd>
FILE_SHARE_WRITE
</dd>
<dd>
FILE_SHARE_DELETE
</dd>
</dl>

### -param FileObject [in, out]

A pointer to the file object for which to check access for the current open request.

### -param ShareAccess [in, out]

A pointer to the common share-access data structure that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param LinkShareAccess [in, out, optional]

A pointer to the common link share-access data structure (<a href="kernel.link_share_access">LINK_SHARE_ACCESS</a>) that is associated with <i>FileObject</i>. Drivers should treat this structure as opaque.

### -param IoShareAccessFlags [in]

A bitmask of these flags:
IO_SHARE_ACCESS_NO_WRITE_PERMISSION        (0x80000000) specifies that the user has no write permission for the file. This flag is used to prevent opening a file for exclusive read access 
when the user does not have appropriate permissions. 
IO_CHECK_SHARE_ACCESS_UPDATE_SHARE_ACCESS  (0x00000001) indicates whether the SHARE_ACCESS structure
is updated.

## -returns
The <b>IoCheckLinkShareAccess</b> routine returns STATUS_SUCCESS if the requester's access to the file object is compatible with the way in which it is currently open. If the request is denied because of a sharing violation, then STATUS_SHARING_VIOLATION is returned. 

## -remarks
    The <i>ShareAccess</i> parameter must be locked against other accesses
    from other threads while this routine is executing.  Otherwise the counts
    can be synchronization.

## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client
</th>
<td width="70%">
Windows 10, version 1709
</td>
</tr>
<tr>
<th width="30%">
Minimum supported server
</th>
<td width="70%">
Windows Server 2016
</td>
</tr>
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
<dt>Wdm.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ntoskrnl.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.i_o_manager_routines">I/O Manager Routines</a>
</dt>
<dt>
<a href="kernel.iosetlinkshareaccess">IoSetLinkShareAccess</a>
</dt>
<dt>
<a href="kernel.ioupdatelinkshareaccess">IoUpdateLinkShareAccess</a>
</dt>
<dt>
<a href="kernel.ioremovelinkshareaccess">IoRemoveLinkShareAccess</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoCheckLinkShareAccess function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
