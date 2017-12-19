---
UID: NF.ntifs.IoSetTopLevelIrp
title: IoSetTopLevelIrp function
author: windows-driver-content
description: The IoSetTopLevelIrp routine sets the value of the TopLevelIrp field of the current thread.
old-location: ifsk\iosettoplevelirp.htm
old-project: ifsk
ms.assetid: 10d1889b-d79c-4c06-a012-77414c88ce17
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IoSetTopLevelIrp
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
req.alt-api: IoSetTopLevelIrp
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

# IoSetTopLevelIrp function



## -description
The <b>IoSetTopLevelIrp</b> routine sets the value of the <b>TopLevelIrp</b> field of the current thread.



## -syntax

````
VOID IoSetTopLevelIrp(
  _In_opt_ PIRP Irp
);
````


## -parameters

### -param Irp [in, optional]

I/O request packet (IRP) pointer to be stored in the <b>TopLevelIrp</b> field of the current thread.


## -returns
None


## -remarks
<b>IoSetTopLevelIrp</b> sets the value of the <b>TopLevelIrp</b> field in the thread object for the current thread. This value can be <b>NULL</b>, a pointer to the current IRP, or an FSRTL flag. For more information about these values and what they mean, see the reference entry for <a href="ifsk.iogettoplevelirp">IoGetTopLevelIrp</a>.

Only file systems can call <b>IoSetTopLevelIrp</b>. File system filters and minifilters cannot safely call this routine, because doing so can cause deadlocks. 


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
<a href="ifsk.iogettoplevelirp">IoGetTopLevelIrp</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20IoSetTopLevelIrp routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

