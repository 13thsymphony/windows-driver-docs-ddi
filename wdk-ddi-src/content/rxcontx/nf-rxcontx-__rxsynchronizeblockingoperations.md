---
UID : NF:rxcontx.__RxSynchronizeBlockingOperations
title : __RxSynchronizeBlockingOperations function
author : windows-driver-content
description : __RxSynchronizeBlockingOperations synchronizes blocking I/O requests to the same work queue.
old-location : ifsk\__rxsynchronizeblockingoperations.htm
old-project : ifsk
ms.assetid : e957f8bc-2ce3-4b9c-819e-ee068b39c4a0
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : __RxSynchronizeBlockingOperations
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : rxcontx.h
req.include-header : Rxcontx.h
req.target-type : Desktop
req.target-min-winverclnt : The __RxSynchronizeBlockingOperations routine is only available on Windows Server 2003.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : __RxSynchronizeBlockingOperations
req.alt-loc : rxcontx.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : "*LPRILWRITEPHONEBOOKENTRYPARAMS, RILWRITEPHONEBOOKENTRYPARAMS"
req.product : Windows 10 or later.
---


# __RxSynchronizeBlockingOperations function
<b>__RxSynchronizeBlockingOperations</b> synchronizes blocking I/O requests to the same work queue.

## Syntax

````
NTSTATUS __RxSynchronizeBlockingOperations(
  _Inout_ PRX_CONTEXT RxContext,
  _In_    PFCB        Fcb,
  _Inout_ PLIST_ENTRY BlockingIoQ,
  _In_    BOOLEAN     DropFcbLock
);
````

## Parameters

`RxContext`

A pointer to the RX_CONTEXT of the operation being synchronized.

`Fcb`

A pointer to the FCB.

`BlockingIoQ`

A pointer to the LIST_ENTRY for the queue.

`DropFcbLock`

A Boolean value that indicates if the FCB resource should be released. If this parameter is <b>TRUE</b>, then the FCB resource will be released.


## Return Value

<b>__RxSynchronizeBlockingOperations</b> returns STATUS_SUCCESS on success or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>The I/O request and the associated RX_CONTEXT was canceled.
<dl>
<dt><b>STATUS_PENDING</b></dt>
</dl>The <i>RxContext</i> was for an asynchronous operation and the <i>RxContext</i> has been added to the queue.

## Remarks

The<b> __RxSynchronizeBlockingOperations</b> routine synchronizes blocking I/O requests to the same work queue. RDBSS uses <b>__RxSynchronizeBlockingOperations</b> internally to synchronize named pipe operations. The work queue is the queue referenced by the file object extension (FOBX) associated with the <i>Fcb</i>. 

A network mini-redirector may use <b>__RxSynchronizeBlockingOperations</b> to synchronize operations on a separate queue that is maintained by the network mini-redirector. 

If <i>RxContext</i> is marked for an asynchronous operation, <b>__RxSynchronizeBlockingOperations</b> will add the <i>RxContext</i> to the queue and return STATUS_PENDING. If <i>RxContext</i> is marked for a synchronous operation, <b>__RxSynchronizeBlockingOperations</b> will block and <i>RxContext</i> is resumed when a call is made to <a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>. 

If the blocking I/O request was canceled, <b>__RxSynchronizeBlockingOperations</b> returns STATUS_CANCELLED to indicate the error.

The <b>SyncEvent</b> member of the RX_CONTEXT structure pointed to by <i>RxContext</i> must have been reset before calling <b>__RxSynchronizeBlockingOperations</b>. The FCB resource must be locked before calling <b>__RxSynchronizeBlockingOperations</b> if the <i>DropFcbLock</i> parameter is set to <b>TRUE</b>. 

The following two macros are defined on Windows Server 2003 or later for calling <b>__RxSynchronizeBlockingOperations</b>:

<b>RxSynchronizeBlockingOperations</b> - calls with the <i>DropFcbLock</i> parameter set to <b>FALSE</b>. 

<b>RxSynchronizeBlockingOperationsAndDropFcbLock</b> - calls with the <i>DropFcbLock</i> parameter set to <b>TRUE</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rxcontx.h (include Rxcontx.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxcompleterequest_real.md">RxCompleteRequest_Real</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxcreaterxcontext.md">RxCreateRxContext</a>
</dt>
<dt>
<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxdereferenceanddeleterxcontext_real.md">RxDereferenceAndDeleteRxContext_Real</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxinitializecontext.md">RxInitializeContext</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxpreparecontextforreuse.md">RxPrepareContextForReuse</a>
</dt>
<dt>
<a href="..\rxcontx\nf-rxcontx-rxresumeblockedoperations_serially.md">RxResumeBlockedOperations_Serially</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff557382">__RxSynchronizeBlockingOperationsMaybeDroppingFcbLock</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20__RxSynchronizeBlockingOperations function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>