---
UID: NF.ntifs.IoGetTopLevelIrp
title: IoGetTopLevelIrp function
author: windows-driver-content
description: The IoGetTopLevelIrp routine returns the value of the TopLevelIrp field of the current thread.
old-location: ifsk\iogettoplevelirp.htm
old-project: ifsk
ms.assetid: e92685f6-031a-464a-b26a-54bebf7d66b6
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IoGetTopLevelIrp
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
req.alt-api: IoGetTopLevelIrp
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
---

# IoGetTopLevelIrp function



## -description
The <b>IoGetTopLevelIrp</b> routine returns the value of the <b>TopLevelIrp</b> field of the current thread.



## -syntax

````
PIRP IoGetTopLevelIrp(
   VOID 
);
````


## -parameters

### -param  

None


## -returns
<b>IoGetTopLevelIrp</b> returns the value of the <b>TopLevelIrp</b> field of the current thread.


## -remarks
<b>IoGetTopLevelIrp</b> can return <b>NULL</b>, an arbitrary file-system-specific value (such as a pointer to the current IRP), or one of the flags listed in the following table.

If the current thread holds no resources above the file system, <b>IoGetTopLevelIrp</b> returns <b>NULL</b>.

If the file system is the top-level component for the current thread, <b>IoGetTopLevelIrp</b> returns a pointer to the current IRP.

If a component other than the file system is the top-level component for the current thread, <b>IoGetTopLevelIrp</b> returns one of the following flags: 

FSRTL_FSP_TOP_LEVEL_IRP

This is a recursive call.

FSRTL_CACHE_TOP_LEVEL_IRP

The cache manager is the top-level component for the current thread.

FSRTL_MOD_WRITE_TOP_LEVEL_IRP

The modified page writer is the top-level component for the current thread.

FSRTL_FAST_IO_TOP_LEVEL_IRP

The cache manager is the top-level component for the current thread, and the current thread is in a fast I/O path.


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
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.iosettoplevelirp">IoSetTopLevelIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoGetTopLevelIrp routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

