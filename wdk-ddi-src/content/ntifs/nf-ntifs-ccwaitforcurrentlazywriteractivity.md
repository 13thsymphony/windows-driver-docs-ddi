---
UID: NF.ntifs.CcWaitForCurrentLazyWriterActivity
title: CcWaitForCurrentLazyWriterActivity function
author: windows-driver-content
description: The CcWaitForCurrentLazyWriterActivity routine puts the caller into a wait state until the current batch of lazy writer activity is completed.
old-location: ifsk\ccwaitforcurrentlazywriteractivity.htm
old-project: ifsk
ms.assetid: eda2198d-d9c9-498a-b94f-5ebdaae417be
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: CcWaitForCurrentLazyWriterActivity
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available on Microsoft Windows 2000 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: CcWaitForCurrentLazyWriterActivity
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
req.irql: 
---

# CcWaitForCurrentLazyWriterActivity function



## -description
The <b>CcWaitForCurrentLazyWriterActivity</b> routine puts the caller into a wait state until the current batch of lazy writer activity is completed.



## -syntax

````
NTSTATUS CcWaitForCurrentLazyWriterActivity(void);
````


## -parameters


## -returns
<b>CcWaitForCurrentLazyWriterActivity</b> can return one of the following NTSTATUS values: 
<dl>
<dt>STATUS_SUCCESS</dt>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl><b>CcWaitForCurrentLazyWriterActivity</b> can return one of the following NTSTATUS values: 
<dl>
<dt>STATUS_SUCCESS</dt>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl><b>CcWaitForCurrentLazyWriterActivity</b> can return one of the following NTSTATUS values: 
<dl>
<dt>STATUS_SUCCESS</dt>
<dt>STATUS_INSUFFICIENT_RESOURCES</dt>
</dl>

## -remarks
<b>CcWaitForCurrentLazyWriterActivity</b> puts the calling thread into a wait state until all work items currently in the lazy writer (read ahead or write behind) work queue have completed.

To prevent deadlock, the caller should release any currently held synchronization objects before calling <b>CcWaitForCurrentLazyWriterActivity</b>.


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
Available on Microsoft Windows 2000 and later. 

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
</table>

## -see-also
<dl>
<dt>
<a href="ifsk.ccinitializecachemap">CcInitializeCacheMap</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff539191">CcReadAhead</a>
</dt>
<dt>
<a href="ifsk.ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>
</dt>
<dt>
<a href="ifsk.ccsetreadaheadgranularity">CcSetReadAheadGranularity</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20CcWaitForCurrentLazyWriterActivity routine%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

