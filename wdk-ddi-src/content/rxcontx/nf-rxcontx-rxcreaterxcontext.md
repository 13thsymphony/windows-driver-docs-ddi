---
UID: NF.rxcontx.RxCreateRxContext
title: RxCreateRxContext
author: windows-driver-content
description: RxCreateRxContext allocates a new RX_CONTEXT structure and initializes the data structure.
old-location: ifsk\rxcreaterxcontext.htm
old-project: ifsk
ms.assetid: ff39aebb-03c0-4ba4-844a-417579ed2bbf
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: RxCreateRxContext
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
req.alt-api: RxCreateRxContext
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

# RxCreateRxContext function



## -description
<p><b>RxCreateRxContext</b> allocates a new RX_CONTEXT structure and initializes the data structure. </p>


## -syntax

````
PRX_CONTEXT RxCreateRxContext(
  _In_opt_ PIRP                 Irp,
  _In_     PRDBSS_DEVICE_OBJECT RxDeviceObject,
  _In_     ULONG                InitialContextFlags
);
````


## -parameters
<dl>

### -param Irp [in, optional]

<dd>
<p>A pointer to the IRP to be encapsulated by this RX_CONTEXT structure.</p>
</dd>

### -param RxDeviceObject [in]

<dd>
<p>A pointer to the device object to which this RX_CONTEXT and IRP apply.</p>
</dd>

### -param InitialContextFlags [in]

<dd>
<p>The set of initial values for the <b>Flags</b> member of the RX_CONTEXT data structure to be stored in the RX_CONTEXT structure. These initial values can be any combination of the following enumerations:</p>
<p></p>
<dl>

### -param RX_CONTEXT_FLAG_WAIT 

<dd>
<p>When this value is set, the IRP should be not be posted for later execution by the file system process, but should be waited on to complete.</p>
</dd>

### -param RX_CONTEXT_FLAG_MUST_SUCCEED

<dd>
<p>When this value is set, the operation must succeed. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers. </p>
</dd>

### -param RX_CONTEXT_FLAG_MUST_SUCCEED_NONBLOCKING

<dd>
<p>When this value is set, the operation must succeed for non-blocking operations. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers. </p>
</dd>
</dl>
</dd>
</dl>

## -returns
<p><b>RxCreateRxContext</b> returns a pointer to an allocated RX_CONTEXT data structure on success or a <b>NULL</b> pointer on failure. </p>

## -remarks
<p><b>RxCreateRxContext</b> calls <a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a> to initialize the newly created RX_CONTEXT structure before returning. </p>

<p><b>RxCreateRxContext</b> allocates non-paged pool memory when creating a new RX_CONTEXT data structure and sets the following value in the Flags member of the RX_CONTEXT:</p>

<p></p>

<p>When this value is set, the RX_CONTEXT structure was allocated from non-paged pool memory.</p>

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
<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext-real.md">RxDereferenceAndDeleteRxContext_Real</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>
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
<dt>
<a href="..\rxcontx\ns-rxcontx--rx-context.md">RX_CONTEXT</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateRxContext function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
