---
UID: NF:wdm.ExGetSharedWaiterCount
title: ExGetSharedWaiterCount function
author: windows-driver-content
description: The ExGetSharedWaiterCount routine returns the number of waiters on shared access to a given resource.
old-location: kernel\exgetsharedwaitercount.htm
old-project: kernel
ms.assetid: a9ca60a7-9bec-4c44-8803-85e183b48b01
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ExGetSharedWaiterCount
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
req.alt-api: ExGetSharedWaiterCount
req.alt-loc: NtosKrnl.exe
req.ddi-compliance: HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
req.typenames: WORK_QUEUE_TYPE
req.product: Windows 10 or later.
---

# ExGetSharedWaiterCount function



## -description
The <b>ExGetSharedWaiterCount</b> routine returns the number of waiters on shared access to a given resource. 



## -syntax

````
ULONG ExGetSharedWaiterCount(
  _In_ PERESOURCE Resource
);
````


## -parameters

### -param Resource [in]

A pointer to the resource to be tested. 


## -returns
<b>ExGetSharedWaiterCount</b> returns the number of threads currently waiting to acquire the given resource for shared access. 


## -remarks
<b>ExGetSharedWaiterCount</b> can be called to get an estimate of how many other threads might be waiting to read the data protected by a particular resource variable. The caller cannot assume that the returned value remains constant for any particular interval.


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
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/hh454220">HwStorPortProhibitedDDIs</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-exacquireresourceexclusivelite.md">ExAcquireResourceExclusiveLite</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exacquireresourcesharedlite.md">ExAcquireResourceSharedLite</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exacquiresharedstarveexclusive.md">ExAcquireSharedStarveExclusive</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exacquiresharedwaitforexclusive.md">ExAcquireSharedWaitForExclusive</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exgetexclusivewaitercount.md">ExGetExclusiveWaiterCount</a>
</dt>
<dt>
<a href="..\wdm\nf-wdm-exreleaseresourceforthreadlite.md">ExReleaseResourceForThreadLite</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20ExGetSharedWaiterCount routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

