---
UID: NF.rxcontx.RxPrepareContextForReuse
title: RxPrepareContextForReuse
author: windows-driver-content
description: RxPrepareContextForReuse prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the ReferenceCount member to the RX_CONTEXT structure is set to zero).
old-location: ifsk\rxpreparecontextforreuse.htm
old-project: ifsk
ms.assetid: 16b4bd82-0ffc-40c7-8cd2-f73a2a588ac8
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxPrepareContextForReuse
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxcontx.h
req.include-header: Rxprocs.h  rxcontx.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: RxPrepareContextForReuse
req.alt-loc: rxcontx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= APC_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# RxPrepareContextForReuse function



## -description
<p><b>RxPrepareContextForReuse</b> prepares an RX_CONTEXT data structure for reuse by resetting all of the operation-specific allocations and acquisitions that have been made (the <b>ReferenceCount</b> member to the RX_CONTEXT structure is set to zero). Parameters that have been obtained from the IRP are not modified. </p>


## -syntax

````
VOID RxPrepareContextForReuse(
  _Inout_ PRX_CONTEXT RxContext
);
````


## -parameters
<dl>

### -param RxContext [in, out]

<dd>
<p>A pointer to the RX_CONTEXT structure.</p>
</dd>
</dl>

## -returns
<p>None </p>

## -remarks
<p>The <b>RxPrepareContextForReuse</b> routine checks that several operation-specific members in the RX_CONTEXT structure are <b>NULL</b> before setting the <b>ReferenceCount</b> member to zero. These operation-specific tests that must be met include the following:</p>

<p>If the <b>MajorFunction</b> member of the associated IRP is IRP_MJ_CREATE, then the <b>Create.CanonicalNameBuffer</b> member must be <b>NULL</b>.</p>

<p>If the <b>MajorFunction</b> member of the associated IRP is IRP_MJ_READ or IRP_MJ_WRITE, then the <b>RxContextSerializationQLinks.Flink</b> and <b>RxContextSerializationQLinks.Blink</b> members must be <b>NULL</b>.</p>

<p>If either of the above conditions are not met, <b>RxPrepareContextForReuse</b> causes the system to ASSERT on checked builds.</p>

<p>The <b>RxPrepareContextForReuse </b>routine would normally only be used by network mini-redirector drivers that reinitialize RX_CONTEXT structures directly. </p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Rxcontx.h (include Rxprocs.h and rxcontx.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= APC_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxcompleterequest.md">RxCompleteRequest</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxcompleterequest-real.md">RxCompleteRequest_Real</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext-real.md">RxDereferenceAndDeleteRxContext_Real</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations-serially.md">RxResumeBlockedOperations_Serially</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx---rxsynchronizeblockingoperations.md">__RxSynchronizeBlockingOperations</a>
</dt>
<dt>
<a href="ifsk.__rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPrepareContextForReuse function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
