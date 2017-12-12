---
UID: NF.ks.KsDecrementCountedWorker
title: KsDecrementCountedWorker function
author: windows-driver-content
description: Decrements the current worker count of a worker previous created by KsRegisterCountedWorker. This should be called after each task within a worker has been completed.
old-location: stream\ksdecrementcountedworker.htm
old-project: stream
ms.assetid: 2b38e4df-e5b6-480b-bd4e-62e059e26411
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsDecrementCountedWorker
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ks.h
req.include-header: Ks.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KsDecrementCountedWorker
req.alt-loc: Ks.lib,Ks.dll
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ks.lib
req.dll: 
req.irql: 
---

# KsDecrementCountedWorker function



## -description
Decrements the current worker count of a worker previous created by <a href="stream.ksregistercountedworker">KsRegisterCountedWorker</a>. This should be called after each task within a worker has been completed. 



## -syntax

````
ULONG KsDecrementCountedWorker(
  _In_ PKSWORKER Worker
);
````


## -parameters

### -param Worker [in]

Contains the previously allocated worker.


## -returns
Returns the current counter. A count of zero implies that the task list has been completed.


## -remarks
<b>KsDecrementCountedWorker</b> should be called after each task within a worker has been completed. A corresponding call to <a href="stream.ksincrementcountedworker">KsIncrementCountedWorker</a> would have previously incremented the count. <b>KsDecrementCountedWorker</b> may be called at DISPATCH_LEVEL.


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
<dt>Ks.h (include Ks.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ks.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksincrementcountedworker">KsIncrementCountedWorker</a>
</dt>
<dt>
<a href="stream.ksregistercountedworker">KsRegisterCountedWorker</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsDecrementCountedWorker function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

