---
UID: NF.ks.KsRemoveSpecificIrpFromCancelableQueue
title: KsRemoveSpecificIrpFromCancelableQueue function
author: windows-driver-content
description: The KsRemoveSpecificIrpFromCancelableQueue function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using KsRemoveIrpFromCancelableQueue, but that was not actually removed from the queue.
old-location: stream\ksremovespecificirpfromcancelablequeue.htm
old-project: stream
ms.assetid: 2d3550c3-4a06-410e-9ec9-fed8b2786092
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: KsRemoveSpecificIrpFromCancelableQueue
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
req.alt-api: KsRemoveSpecificIrpFromCancelableQueue
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

# KsRemoveSpecificIrpFromCancelableQueue function



## -description
The <b>KsRemoveSpecificIrpFromCancelableQueue</b> function removes the specified IRP from the specified queue. This is performed on an IRP that was previously acquired using <a href="stream.ksremoveirpfromcancelablequeue">KsRemoveIrpFromCancelableQueue</a>, but that was not actually removed from the queue. 



## -syntax

````
VOID KsRemoveSpecificIrpFromCancelableQueue(
  _In_ PIRP Irp
);
````


## -parameters

### -param Irp [in]

Points to I/O request packet.


## -returns
None


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