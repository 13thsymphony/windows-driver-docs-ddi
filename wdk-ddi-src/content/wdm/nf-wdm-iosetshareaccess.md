---
UID: NF.wdm.IoSetShareAccess
title: IoSetShareAccess function
author: windows-driver-content
description: The IoSetShareAccess routine sets the access rights for sharing the given file object.
old-location: kernel\iosetshareaccess.htm
old-project: kernel
ms.assetid: a686ea04-8a6b-4c4b-be06-73a75c4fc87d
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: IoSetShareAccess
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 2000.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IoSetShareAccess
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: IrqlIoPassive5, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# IoSetShareAccess function



## -description
The <b>IoSetShareAccess</b> routine sets the access rights for sharing the given file object.


## -syntax

````
VOID IoSetShareAccess(
  _In_    ACCESS_MASK   DesiredAccess,
  _In_    ULONG         DesiredShareAccess,
  _Inout_ PFILE_OBJECT  FileObject,
  _Out_   PSHARE_ACCESS ShareAccess
);
````


## -parameters

### -param DesiredAccess [in]

Specifies an <a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a> value that represents the type of access requested for the <i>FileObject</i>. See <a href="kernel.iocreatefile">IoCreateFile</a> for a complete list of system-defined <i>DesiredAccess </i>flags.

### -param DesiredShareAccess [in]

Specifies the type of share access to be set for the file object. This value can be zero, or any combination of the following:
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

Pointer to the file object whose share access is being set or reset.

### -param ShareAccess [out]

Pointer to the SHARE_ACCESS structure associated with <i>FileObject</i>. Drivers should treat this structure as opaque. 

## -returns
None

## -remarks
Only highest-level kernel-mode drivers should call this routine. The call must occur in the context of the first thread that attempts to open the <i>FileObject</i>.

This routine sets the access and share access information when the <i>FileObject</i> is first opened. It returns a pointer to the common share-access data structure associated with <i>FileObject</i>. Callers should save this pointer for later use when updating the access or closing the file.

Generally, file system drivers (FSDs) are most likely to call this routine. However, other highest-level drivers can call <b>IoSetShareAccess</b> to control the kind of access allowed to a driver-created device object associated with the given <i>FileObject</i>.

<b>IoSetShareAccess</b> is not an atomic operation. Therefore, drivers calling this routine must protect the shared file object passed to <b>IoSetShareAccess </b>by means of some kind of lock, such as a mutex or a resource lock, in order to prevent corruption of the shared access counts.

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
Available starting with Windows 2000.
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
PASSIVE_LEVEL
</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules
</th>
<td width="70%">
<a href="devtest.wdm_irqliopassive5">IrqlIoPassive5</a>, <a href="devtest.storport_hwstorportprohibitedddis">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540466">ACCESS_MASK</a>
</dt>
<dt>
<a href="kernel.iocreatefile">IoCreateFile</a>
</dt>
<dt>
<a href="ifsk.iocreatefileex">IoCreateFileEx</a>
</dt>
<dt>
<a href="kernel.iocheckshareaccess">IoCheckShareAccess</a>
</dt>
<dt>
<a href="kernel.iogetfileobjectgenericmapping">IoGetFileObjectGenericMapping</a>
</dt>
<dt>
<a href="kernel.iogetrelateddeviceobject">IoGetRelatedDeviceObject</a>
</dt>
<dt>
<a href="kernel.ioremoveshareaccess">IoRemoveShareAccess</a>
</dt>
<dt>
<a href="kernel.ioupdateshareaccess">IoUpdateShareAccess</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20IoSetShareAccess routine%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
