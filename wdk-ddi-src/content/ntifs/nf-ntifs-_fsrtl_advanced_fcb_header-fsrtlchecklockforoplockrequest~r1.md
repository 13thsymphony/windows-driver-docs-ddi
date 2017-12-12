---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlCheckLockForOplockRequest~r1
title: FsRtlCheckLockForOplockRequest function
author: windows-driver-content
description: The FsRtlCheckLockForOplockRequest routine checks for locks within the allocation size of a file. The file lock object is checked for the presence of byte range locks that would prevent an oplock request from being granted.
old-location: ifsk\fsrtlchecklockforoplockrequest.htm
old-project: ifsk
ms.assetid: 67056CD0-EBFB-4E34-9613-98ECBB858810
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlCheckLockForOplockRequest
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
req.alt-api: FsRtlCheckLockForOplockRequest
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
---

# FsRtlCheckLockForOplockRequest function



## -description
The <b>FsRtlCheckLockForOplockRequest</b> routine checks for locks within the allocation size of a file. The file lock object is  checked for the presence of  byte range locks that would prevent an oplock request from being granted.



## -syntax

````
BOOLEAN FsRtlCheckLockForOplockRequest(
  _In_ PFILE_LOCK     FileLock,
  _In_ PLARGE_INTEGER AllocationSize
);
````


## -parameters

### -param FileLock [in]

The file lock that specifies locked ranges.


### -param AllocationSize [in]

The file allocation size to check for any locked ranges.


## -returns
<b>FsRtlCheckLockForOplockRequest</b> returns <b>TRUE</b> if the  oplock request can be granted;  <b> FALSE</b> otherwise.


## -remarks
<b>FsRtlCheckLockForOplockRequest</b> returns <b>TRUE</b> if <i>AllocationSize</i> = 0.

If <i>FileLock</i> has any pending lock requests, the check fails and <b>FsRtlCheckLockForOplockRequest</b> returns <b>FALSE</b>.


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
&lt;= APC_LEVEL

</td>
</tr>
</table>