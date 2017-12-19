---
UID: NF.rxcontx.RxInitializeContext
title: RxInitializeContext function
author: windows-driver-content
description: RxInitializeContext initializes an existing RX_CONTEXT data structure.
old-location: ifsk\rxinitializecontext.htm
old-project: ifsk
ms.assetid: 71b595be-61ac-4a8f-af5e-d504e5091e0c
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: RxInitializeContext
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
req.alt-api: RxInitializeContext
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
req.product: Windows 10 or later.
---

# RxInitializeContext function



## -description
<b>RxInitializeContext</b> initializes an existing RX_CONTEXT data structure. 



## -syntax

````
VOID RxInitializeContext(
  _In_opt_ PIRP                 Irp,
  _In_     PRDBSS_DEVICE_OBJECT RxDeviceObject,
  _In_     ULONG                InitialContextFlags,
  _Inout_  PRX_CONTEXT          RxContext
);
````


## -parameters

### -param Irp [in, optional]

A pointer to the IRP to be encapsulated by this RX_CONTEXT structure.


### -param RxDeviceObject [in]

A pointer to the device object to which this RX_CONTEXT and IRP apply.


### -param InitialContextFlags [in]

The set of initial values for <i>Flags</i> member of the RX_CONTEXT data structure to be stored in the RX_CONTEXT structure. These initial values can be any combination of the following enumerations:




### -param RX_CONTEXT_FLAG_WAIT

When this value is set, the IRP should be not be posted for later execution by the file system process, but should be waited on to complete.


### -param RX_CONTEXT_FLAG_MUST_SUCCEED

When this value is set, the operation must succeed. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers. 


### -param RX_CONTEXT_FLAG_MUST_SUCCEED_NONBLOCKING

When this value is set, the operation must succeed for non-blocking operations. This value is not currently used by RDBSS, but it may be used by network mini-redirector drivers. 

</dd>
</dl>

### -param RxContext [in, out]

Pointer to the RX_CONTEXT to be initialized.


## -returns
None 


## -remarks
<b>RxInitializeContext</b> is called internally by the <b>RxCreateRxContext</b> routine. So the <b>RxInitializeContext</b> routine would normally only be used by network min-redirector drivers that allocate RX_CONTEXT structures directly rather than calling the <b>RxCreateRxContext</b> routine to allocate and initialize an RX_CONTEXT structure. 

If the <i>Irp</i> parameter is configured for asynchronous operation, then the <b>Flags</b> member of the RX_CONTEXT structure pointed to by <i>RxContext</i> also has the following value set:



When this value is set, the RX_CONTEXT structure is tagged for asynchronous operation.

RX_CONTEXT_FLAG_ASYNC_OPERATION is also set for the following conditions:

The <b>MajorFunction</b> member of the <i>Irp</i> is IRP_MJ_READ, IRP_MJ_WRITE, or IRP_MJ_DEVICE_CONTROL.

The <b>MajorFunction</b> member of the <i>Irp</i> is an IRP_MJ_DIRECTORY_CONTROL and the <b>MinorFunction</b> member of the <i>IRP</i> is an IRP_MN_NOTIFY_CHANGE_DIRECTORY.

The <b>MajorFunction</b> member of the <i>Irp</i> is an IRP_MJ_FILE_SYSTEM_CONTROL and <b>NetRoot</b> member of the associated FCB is not <b>NULL</b> and the <b>Type</b> member of the NET_ROOT is NET_ROOT_PIPE.

If this is a recursive file system call (the TopLevelIrp member in the thread local storage is the current <i>Irp</i>) then the <b>Flags</b> member of <i>RxContext</i> also has the following value set:

When this value is set, the RX_CONTEXT structure is tagged as a recursive call.

If the <i>RxDeviceObject</i> parameter indicates that this is the top level RDBSS device object, then the <b>Flags</b> member of the RX_CONTEXT structure also has the following value set:

When this value is set, the RX_CONTEXT structure is tagged as using the top level device object.

If the <i>Irp</i> FileObject Flags member has the FO_WRITE_THROUGH option set, then the <b>Flags</b> member of the RX_CONTEXT structure also has the following value set:

When this value is set, the RX_CONTEXT structure is tagged as set to write through mode.

<b>RxInitializeContext</b> sets a number of other members in the RX_CONTEXT structure including the following:

Sets the proper <b>NodeTypeCode</b>, <b>NodeByteSize</b>, <b>SerialNumber</b>, <b>RxDeviceObject</b>, and initializes the <b>ReferenceCount</b> to 1.

Initializes the SyncEvent

Initialize the associated ScavengerEntry

Initializes the list entry of BlockedOperations

Sets the RX_CONTEXT members based on the <i>Irp</i>. These include <b>CurrentIrp</b>, <b>OriginalThread</b>, <b>MajorFunction</b>, <b>MinorFunction</b>, <b>CurrentIrpSp</b>, <b>pFcb</b>, <b>NonPagedFcb</b>, <b>pFobx</b>, <b>pRelevantSrvOpen</b>, and <b>FobxSerialNumber</b> members.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Rxcontx.h (include Rxprocs.h and rxcontx.h)</dt>
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
<a href="ifsk.rxcompleterequest">RxCompleteRequest</a>
</dt>
<dt>
<a href="ifsk.rxcompleterequest_real">RxCompleteRequest_Real</a>
</dt>
<dt>
<a href="ifsk.rxcreaterxcontext">RxCreateRxContext</a>
</dt>
<dt>
<a href="ifsk.rxdereference">RxDereference</a>
</dt>
<dt>
<a href="ifsk.rxdereferenceanddeleterxcontext_real">RxDereferenceAndDeleteRxContext_Real</a>
</dt>
<dt>
<a href="ifsk.rxpreparecontextforreuse">RxPrepareContextForReuse</a>
</dt>
<dt>
<a href="ifsk.rxresumeblockedoperations_serially">RxResumeBlockedOperations_Serially</a>
</dt>
<dt>
<a href="ifsk.__rxsynchronizeblockingoperations">__RxSynchronizeBlockingOperations</a>
</dt>
<dt>
<a href="ifsk.__rxsynchronizeblockingoperationsmaybedroppingfcblock">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
</dt>
<dt>
<a href="ifsk.rx_context">RX_CONTEXT</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxInitializeContext function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

