---
UID: NF:ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlCurrentBatchOplock
title: FsRtlCurrentBatchOplock function
author: windows-driver-content
description: A file system or filter driver calls FsRtlCurrentBatchOplock to determine whether there are any batch or filter opportunistic locks (oplocks) on a file.
old-location: ifsk\fsrtlcurrentbatchoplock.htm
old-project: ifsk
ms.assetid: cfa02246-12ac-4229-bcdb-4792eb5cb0e7
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FsRtlCurrentBatchOplock
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
req.alt-api: FsRtlCurrentBatchOplock
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
req.typenames: TOKEN_TYPE
---

# FsRtlCurrentBatchOplock function



## -description
A file system or filter driver calls <b>FsRtlCurrentBatchOplock</b> to determine whether there are any batch or filter opportunistic locks (oplocks) on a file. 



## -syntax

````
BOOLEAN FsRtlCurrentBatchOplock(
  _In_ POPLOCK Oplock
);
````


## -parameters

### -param Oplock [in]

Opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>. 


## -returns
<b>FsRtlCurrentBatchOplock</b> returns <b>TRUE</b> if there are current outstanding batch or filter opportunistic locks; <b>FALSE</b> otherwise. 


## -remarks
<b>FsRtlCurrentBatchOplock</b> returns <b>FALSE</b> if no batch or filter opportunistic locks are currently held. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a> instead of <b>FsRtlCurrentBatchOplock</b>. 


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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= APC_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-fsrtlcheckoplock.md">FsRtlCheckOplock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtloplockfsctrl~r2.md">FsRtlOplockFsctrl</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-fsrtloplockisfastiopossible.md">FsRtlOplockIsFastIoPossible</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md">FsRtlUninitializeOplock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCurrentBatchOplock function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

