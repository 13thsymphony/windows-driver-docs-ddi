---
UID : NF:rxworkq.RxPostToWorkerThread
title : RxPostToWorkerThread function
author : windows-driver-content
description : RxPostToWorkerThread invokes a routine passed as a parameter in the context of a worker thread. Memory for the WORK_QUEUE_ITEM must be allocated by the caller.
old-location : ifsk\rxposttoworkerthread.htm
old-project : ifsk
ms.assetid : 0fc9fb57-219e-4a3d-bc82-904ab8657d66
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : RxPostToWorkerThread
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : rxworkq.h
req.include-header : Rxworkq.h, Rxstruc.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : RxPostToWorkerThread
req.alt-loc : rxworkq.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= APC_LEVEL
req.typenames : RX_CONTEXT, *PRX_CONTEXT
req.product : Windows 10 or later.
---


# RxPostToWorkerThread function
<b>RxPostToWorkerThread</b> invokes a routine passed as a parameter in the context of a worker thread. Memory for the WORK_QUEUE_ITEM must be allocated by the caller.

## Syntax

````
NTSTATUS RxPostToWorkerThread(
  _In_ PRDBSS_DEVICE_OBJECT     pMRxDeviceObject,
  _In_ WORK_QUEUE_TYPE          WorkQueueType,
  _In_ PRX_WORK_QUEUE_ITEM      pWorkQueueItem,
  _In_ PRX_WORKERTHREAD_ROUTINE Routine,
  _In_ PVOID                    pContext
);
````

## Parameters

`pMRxDeviceObject`

A pointer to the device object of the corresponding network mini-redirector driver.

`WorkQueueType`

The type of the work queue that represents the priority of the task. This parameter can be one of the following values:

`pWorkQueueItem`

A pointer to WORK_QUEUE_ITEM.

`Routine`

A pointer to the routine to invoke.

`pContext`

A pointer to a context parameter associated with the work item to complete that is passed to the driver.


## Return Value

<b>RxDispatchToWorkerThread</b> returns STATUS_SUCCESS on success or one of the following error code on failure: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>The item could not be dispatched.

## Remarks

There are two common cases of dispatching operations to worker threads. The trade-off between the following two dispatching operations is time versus space (memory usage):

When an operation is going to be repeatedly dispatched, time is conserved by allocating in advance the WORK_QUEUE_ITEM structure as part of the data structure to be dispatched. In this case, use the <b>RxPostToWorkerThread</b> routine. 

For an infrequent operation, you can conserve space by dynamically allocating and freeing memory for the work queue item when it is needed. In this case, use the <a href="..\rxworkq\nf-rxworkq-rxdispatchtoworkerthread.md">RxDispatchToWorkerThread</a> routine. 

The <b>RxPostToWorkerThread</b> routine invokes a routine in the context of a worker thread. The memory for the WORK_QUEUE_ITEM structure must be allocated from non-paged pool memory by the calling routine. 

The current implementation of the <b>RxPostToWorkerThread </b>routine queues work onto the same processor from which the call originated. 

If the <b>RxPostToWorkerThread </b>routine fails on a debug build, the <a href="..\rxlog\nf-rxlog-_rxlog.md">_RxLog</a> routine is called with details of the error. If the <b>RxPostToWorkerThread </b>routine fails and WMI is enabled in the kernel, details of the error will be logged with WMI.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | rxworkq.h (include Rxworkq.h, Rxstruc.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= APC_LEVEL |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\rxlog\nf-rxlog-_rxlog.md">_RxLog</a>
</dt>
<dt>
<a href="..\rxworkq\nf-rxworkq-rxdispatchtoworkerthread.md">RxDispatchToWorkerThread</a>
</dt>
<dt>
<a href="..\rxworkq\nf-rxworkq-rxspindownmrxdispatcher.md">RxSpinDownMRxDispatcher</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxPostToWorkerThread routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>