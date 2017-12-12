---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlCurrentOplockH
title: FsRtlCurrentOplockH function
author: windows-driver-content
description: A file system or filter driver calls FsRtlCurrentOplockH to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file.
old-location: ifsk\fsrtlcurrentoplockh.htm
old-project: ifsk
ms.assetid: 98eb2bef-18ac-449f-b180-7b0f768cc093
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FsRtlCurrentOplockH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlCurrentOplockH routine is available starting with Windows 7.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FsRtlCurrentOplockH
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

# FsRtlCurrentOplockH function



## -description
A file system or filter driver calls <b>FsRtlCurrentOplockH</b> to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file. 



## -syntax

````
BOOLEAN FsRtlCurrentOplockH(
  _In_ POPLOCK Oplock
);
````


## -parameters

### -param Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="ifsk.fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


## -returns
<b>FsRtlCurrentOplockH</b> returns <b>TRUE</b> if there are CACHE_HANDLE_LEVEL opportunistic locks that are currently being held. Otherwise, it returns <b>FALSE</b>. 


## -remarks
<b>FsRtlCurrentOplockH</b> returns <b>FALSE</b> if no CACHE_HANDLE_LEVEL opportunistic locks (oplocks) are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="ifsk.fltcurrentoplockh">FltCurrentOplockH</a> instead of <b>FsRtlCurrentOplock</b>. 


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
The FsRtlCurrentOplockH routine is available starting with Windows 7. 

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
<a href="ifsk.fltcurrentoplockh">FltCurrentOplockH</a>
</dt>
<dt>
<a href="ifsk.fsrtlinitializeoplock">FsRtlInitializeOplock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlCurrentOplockH function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

