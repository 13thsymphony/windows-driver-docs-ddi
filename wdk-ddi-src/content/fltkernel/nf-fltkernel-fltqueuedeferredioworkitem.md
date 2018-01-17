---
UID: NF:fltkernel.FltQueueDeferredIoWorkItem
title: FltQueueDeferredIoWorkItem function
author: windows-driver-content
description: The FltQueueDeferredIoWorkItem routine posts an IRP-based I/O operation to a work queue.
old-location: ifsk\fltqueuedeferredioworkitem.htm
old-project: ifsk
ms.assetid: c6a51b9b-544e-4595-842a-76c667928350
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltQueueDeferredIoWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available in Microsoft Windows 2000 and later versions of all Windows operating systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: FltQueueDeferredIoWorkItem
req.alt-loc: fltmgr.sys
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= DISPATCH_LEVEL
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# FltQueueDeferredIoWorkItem function



## -description
The <b>FltQueueDeferredIoWorkItem</b> routine posts an IRP-based I/O operation to a work queue. 



## -syntax

````
NTSTATUS FltQueueDeferredIoWorkItem(
  _In_ PFLT_DEFERRED_IO_WORKITEM         FltWorkItem,
  _In_ PFLT_CALLBACK_DATA                Data,
  _In_ PFLT_DEFERRED_IO_WORKITEM_ROUTINE WorkerRoutine,
  _In_ WORK_QUEUE_TYPE                   QueueType,
  _In_ PVOID                             Context
);
````


## -parameters

### -param FltWorkItem [in]

A pointer to the work item to add to the work queue. The work item must have been allocated by calling <a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a>. 


### -param Data [in]

A pointer to the callback data (<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>) structure for the I/O operation. The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 


### -param WorkerRoutine [in]

A pointer to a caller-supplied worker routine. This routine is declared as follows: 

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_DEFERRED_IO_WORKITEM_ROUTINE) (
      _in PFLT_DEFERRED_IO_WORKITEM  FltWorkItem,
      __in PFLT_CALLBACK_DATA  CallbackData,
      __in_opt PVOID  Context
      );</pre>
</td>
</tr>
</table></span></div>



### -param FltWorkItem

An opaque pointer to a deferred work item structure. 


### -param CallbackData

A pointer to the callback data structure for the I/O operation. 


### -param Context

An optional context information pointer that was passed as the <i>Context</i> parameter of <b>FltQueueDeferredIoWorkItem</b>. 

</dd>
</dl>

### -param QueueType [in]

This parameter specifies the queue into which the work item that <i>FltWorkItem</i> points to is to be inserted. <i>QueueType</i> can be either of the following. 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>CriticalWorkQueue</b>

</td>
<td>
Insert the work item into the queue from which a system thread with a real-time priority attribute processes the work item. 

</td>
</tr>
<tr>
<td>
<b>DelayedWorkQueue</b>

</td>
<td>
Insert the work item into the queue from which a system thread with a variable priority attribute processes the work item. 

</td>
</tr>
</table>
 

The <i>QueueType</i> value <b>HyperCriticalWorkQueue</b> is reserved for system use. 


### -param Context [in]

A pointer to caller-defined context information to be passed as the <i>Context</i> parameter of the callback routine specified in the <i>WorkerRoutine</i> parameter. 


## -returns
The <b>FltQueueDeferredIoWorkItem</b> routine returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>The target instance for the I/O operation (<i>Data-&gt;Iopb-&gt;TargetInstance</i>) is being torn down. This is an error code. 
<dl>
<dt><b>STATUS_FLT_NOT_SAFE_TO_POST_OPERATION</b></dt>
</dl>The I/O operation cannot be posted safely to a worker thread. Possible reasons include the following: 

<b>FltQueueDeferredIoWorkItem</b> cannot post an I/O operation to a worker thread if the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>, because the resulting file system recursion could cause deadlocks or stack overflows. (For more information, see <a href="..\ntifs\nf-ntifs-iogettoplevelirp.md">IoGetTopLevelIrp</a>.) 

<b>FltQueueDeferredIoWorkItem</b> cannot post a paging I/O operation to a worker thread. 

STATUS_FLT_NOT_SAFE_TO_POST_OPERATION is an error code. 

 


## -remarks
The <b>FltQueueDeferredIoWorkItem</b> routine posts an I/O operation to a system work queue. The specified <i>WorkerRoutine</i> callback routine is called in the context of a system thread, at IRQL PASSIVE_LEVEL. 

The operation must be an IRP-based I/O operation. To determine whether a given callback data structure represents an IRP-based I/O operation, use the <a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a> macro. 

A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a preoperation callback (<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>) routine as follows: 

The preoperation callback calls <a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a> to allocate the work item. 

The preoperation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. 

The preoperation callback returns FLT_PREOP_PENDING. 

After processing the I/O operation, the work routine calls <a href="..\fltkernel\nf-fltkernel-fltcompletependedpreoperation.md">FltCompletePendedPreOperation</a> to return the I/O operation to the Filter Manager. 

The work routine calls <a href="..\fltkernel\nf-fltkernel-fltfreedeferredioworkitem.md">FltFreeDeferredIoWorkItem</a> to free the work item. 

A minifilter driver can use <b>FltQueueDeferredIoWorkItem</b> in a post-operation callback (<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>) routine as follows: 

The post-operation callback calls <a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a> to allocate the work item. 

The post-operation callback calls <b>FltQueueDeferredIoWorkItem</b> to post the operation to the work queue. 

The post-operation callback returns FLT_POSTOP_MORE_PROCESSING_REQUIRED. 

After processing the I/O operation, the work routine calls <a href="..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md">FltCompletePendedPostOperation</a> to return the I/O operation to the Filter Manager. 

IRP_MJ_READ

IRP_MJ_WRITE

IRP_MJ_FLUSH_BUFFERS


## -see-also
<dl>
<dt>
<a href="..\fltkernel\ns-fltkernel-_flt_callback_data.md">FLT_CALLBACK_DATA</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff544654">FLT_IS_IRP_OPERATION</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltallocatedeferredioworkitem.md">FltAllocateDeferredIoWorkItem</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcompletependedpostoperation.md">FltCompletePendedPostOperation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltcompletependedpreoperation.md">FltCompletePendedPreOperation</a>
</dt>
<dt>
<a href="..\fltkernel\nf-fltkernel-fltfreedeferredioworkitem.md">FltFreeDeferredIoWorkItem</a>
</dt>
<dt>
<a href="..\ntifs\nf-ntifs-iogettoplevelirp.md">IoGetTopLevelIrp</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_post_operation_callback.md">PFLT_POST_OPERATION_CALLBACK</a>
</dt>
<dt>
<a href="..\fltkernel\nc-fltkernel-pflt_pre_operation_callback.md">PFLT_PRE_OPERATION_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueueDeferredIoWorkItem routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

