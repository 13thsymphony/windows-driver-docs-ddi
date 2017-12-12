---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlAreThereWaitingFileLocks
title: FsRtlAreThereWaitingFileLocks function
author: windows-driver-content
description: The FsRtlAreThereWaitingFileLocks routine checks a file lock queue for any waiting file locks.
old-location: ifsk\fsrtlaretherewaitingfilelocks.htm
old-project: ifsk
ms.assetid: 92093588-DD44-4503-8803-7E47F178A728
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlAreThereWaitingFileLocks
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
req.alt-api: FsRtlAreThereWaitingFileLocks
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

# FsRtlAreThereWaitingFileLocks function



## -description
The <b>FsRtlAreThereWaitingFileLocks</b> routine checks a file lock queue for any waiting file locks.



## -syntax

````
BOOLEAN FsRtlAreThereWaitingFileLocks(
  _In_ PFILE_LOCK FileLock
);
````


## -parameters

### -param FileLock [in]

The file lock that specifies locked ranges.


## -returns

      Returns <b>TRUE</b> if waiting file  locks are present;  <b>FALSE</b> otherwise.


## -remarks


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