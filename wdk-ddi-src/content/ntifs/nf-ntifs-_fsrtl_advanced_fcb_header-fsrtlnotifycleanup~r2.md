---
UID: NF.ntifs._FSRTL_ADVANCED_FCB_HEADER.FsRtlNotifyCleanup~r2
title: FsRtlNotifyCleanup function
author: windows-driver-content
description: When the last handle to a file object is released, the FsRtlNotifyCleanup routine removes the file object's notify structure, if present, from the specified notify list.
old-location: ifsk\fsrtlnotifycleanup.htm
old-project: ifsk
ms.assetid: 90cc2c3b-8fb2-4450-9c20-06e1e4d1fe47
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: FsRtlNotifyCleanup
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
req.alt-api: FsRtlNotifyCleanup
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

# FsRtlNotifyCleanup function



## -description
When the last handle to a file object is released, the <b>FsRtlNotifyCleanup</b> routine removes the file object's notify structure, if present, from the specified notify list.



## -syntax

````
VOID FsRtlNotifyCleanup(
  _In_ PNOTIFY_SYNC NotifySync,
  _In_ PLIST_ENTRY  NotifyList,
  _In_ PVOID        FsContext
);
````


## -parameters

### -param NotifySync [in]

A pointer to an opaque synchronization object for <i>NotifyList</i>. 


### -param NotifyList [in]

A pointer to the head of a notify list. Each element in the list is an opaque notify structure.


### -param FsContext [in]

A unique value assigned by the file system to identify a notify structure as belonging to a particular file object.


## -returns
None


## -remarks
If a notify structure is found that matches <i>FsContext</i>, <b>FsRtlNotifyCleanup</b> completes all IRPs that are queued in the notify structure. When all the IRPs are completed, <b>FsRtlNotifyCleanup</b> removes the notify structure from the notify list and deallocates it.


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
<a href="ifsk.fsrtlnotifyfilterchangedirectory">FsRtlNotifyFilterChangeDirectory</a>
</dt>
<dt>
<a href="ifsk.fsrtlnotifyfilterreportchange">FsRtlNotifyFilterReportChange</a>
</dt>
<dt>
<a href="ifsk.fsrtlnotifyfullchangedirectory">FsRtlNotifyFullChangeDirectory</a>
</dt>
<dt>
<a href="ifsk.fsrtlnotifyfullreportchange">FsRtlNotifyFullReportChange</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FsRtlNotifyCleanup routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

