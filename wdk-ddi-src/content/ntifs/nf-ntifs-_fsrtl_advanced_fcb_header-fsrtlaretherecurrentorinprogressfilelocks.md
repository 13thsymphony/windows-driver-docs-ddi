---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAreThereCurrentOrInProgressFileLocks
title: FsRtlAreThereCurrentOrInProgressFileLocks function
author: windows-driver-content
description: TheFsRtlAreThereCurrentOrInProgressFileLocks routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.
old-location: ifsk\fsrtlaretherecurrentorinprogressfilelocks.htm
old-project: ifsk
ms.assetid: 9e5e0e37-5f01-4bc3-b660-c65c540af04e
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlAreThereCurrentOrInProgressFileLocks
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows 7 and later versions of the Windows operating system.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlAreThereCurrentOrInProgressFileLocks
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
req.irql: <=APC_LEVEL
req.typenames: TOKEN_TYPE
---

# FsRtlAreThereCurrentOrInProgressFileLocks function



## -description
The<b>FsRtlAreThereCurrentOrInProgressFileLocks </b>routine determines if there are byte range locks assigned to a file or any lock operations in progress for that file.



## -syntax

````
BOOLEAN FsRtlAreThereCurrentOrInProgressFileLocks(
  _In_ PFILE_LOCK FileLock
);
````


## -parameters

### -param FileLock [in]

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a> structure for the file to be checked.


## -returns
The routine returns <b>TRUE</b> when there are any byte range locks assigned to the file or when there are byte range lock requests in progress for the file. Otherwise, the routine returns <b>FALSE</b>.


## -remarks
File systems can use the <b>FsRtlAreThereCurrentOrInProgressFileLocks</b> routine in <a href="https://msdn.microsoft.com/5cbbfecc-2182-40f6-9f54-a8146c1f663f">Oplock Semantics</a> to determine whether to grant a shared oplock.


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
Available in Windows 7 and later versions of the Windows operating system. 

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ntifs.h (include FltKernel.h or Ntifs.h)</dt>
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
&lt;=APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff540328">FILE_LOCK</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlallocatefilelock~r1.md">FsRtlAllocateFileLock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlgetnextfilelock~r1.md">FsRtlGetNextFileLock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializefilelock~r2.md">FsRtlInitializeFileLock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/5cbbfecc-2182-40f6-9f54-a8146c1f663f">Oplock Semantics</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlAreThereCurrentOrInProgressFileLocks routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

