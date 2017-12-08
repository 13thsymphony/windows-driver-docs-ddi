---
UID: NF.ks.KsCancelIo
title: KsCancelIo function
author: windows-driver-content
description: The KsCancelIo function cancels all IRPs on the specified cancel list. If an IRP on the list does not have a cancel routine, only the cancel bit is set in the IRP. The function can be called at IRQ level DISPATCH_LEVEL or lower.
old-location: stream\kscancelio.htm
old-project: stream
ms.assetid: 082a63d5-5ba5-4cd3-aea3-0184317e1e96
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: KsCancelIo
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
req.alt-api: KsCancelIo
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
req.irql: < DISPATCH_LEVEL
---

# KsCancelIo function



## -description
The <b>KsCancelIo</b> function cancels all IRPs on the specified cancel list. If an IRP on the list does not have a cancel routine, only the cancel bit is set in the IRP. The function can be called at IRQ level DISPATCH_LEVEL or lower.


## -syntax

````
void KsCancelIo(
  _Inout_ PLIST_ENTRY QueueHead,
  _In_    PKSPIN_LOCK SpinLock
);
````


## -parameters

### -param QueueHead [in, out]

Specifies the head of a driver-maintained queue containing the IRP's to be canceled.

### -param SpinLock [in]

Points to a caller-allocated spin lock for queue access. A copy of this pointer is kept in the IRP's KSQUEUE_SPINLOCK_IRP_STORAGE(Irp) for use by the cancel routine, if necessary.

## -returns
None

## -remarks
<b>KsCancelIo </b>cancels all IRPs in a given driver-maintained queue. If the IRP has a cancel routine, the cancel routine is called. Otherwise, the cancel flag in the IRP is set to <b>TRUE</b>. The IRPs are not removed from the queue by this routine. It is the sole responsibility of the driver to ensure that the IRPs are removed either by the cancel routine specified in the IRP or by some other driver-supplied functionality.

If the IRP being canceled has a driver-supplied cancel routine, the cancel spin lock can be obtained from the IRP by calling KSQUEUE_SPINLOCK_IRP_STORAGE.

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
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
&lt; DISPATCH_LEVEL
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="stream.ksaddirptocancelablequeue">KsAddIrpToCancelableQueue</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [stream\stream]:%20KsCancelIo function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
