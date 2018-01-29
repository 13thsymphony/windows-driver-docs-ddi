---
UID : NF:fltkernel.FltQueueGenericWorkItem
title : FltQueueGenericWorkItem function
author : windows-driver-content
description : FltQueueGenericWorkItem posts a work item that is not associated with a specific I/O operation to a work queue.
old-location : ifsk\fltqueuegenericworkitem.htm
old-project : ifsk
ms.assetid : 30179fe1-e218-46cd-96a9-816ebab112bf
ms.author : windowsdriverdev
ms.date : 1/9/2018
ms.keywords : fltkernel/FltQueueGenericWorkItem, ifsk.fltqueuegenericworkitem, FltApiRef_p_to_z_221f809d-f028-4e0f-b7b3-1341c1ed8782.xml, FltQueueGenericWorkItem function [Installable File System Drivers], FltQueueGenericWorkItem
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : fltkernel.h
req.include-header : Fltkernel.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : FltMgr.lib
req.dll : Fltmgr.sys
req.irql : <= DISPATCH_LEVEL
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : EXpsFontRestriction
---


# FltQueueGenericWorkItem function
<b>FltQueueGenericWorkItem</b> posts a work item that is not associated with a specific I/O operation to a work queue.

## Syntax

````
NTSTATUS FltQueueGenericWorkItem(
  _In_     PFLT_GENERIC_WORKITEM         FltWorkItem,
  _In_     PVOID                         FltObject,
  _In_     PFLT_GENERIC_WORKITEM_ROUTINE WorkerRoutine,
  _In_     WORK_QUEUE_TYPE               QueueType,
  _In_opt_ PVOID                         Context
);
````

## Parameters

`FltWorkItem`

Pointer to the work item to be added to the work queue. The work item must have been allocated by calling <a href="..\fltkernel\nf-fltkernel-fltallocategenericworkitem.md">FltAllocateGenericWorkItem</a>.

`FltObject`

Opaque filter (PFLT_FILTER) or instance (PFLT_INSTANCE) pointer for the caller.

`WorkerRoutine`

Pointer to a caller-supplied worker routine. This routine is declared as follows: 
<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef VOID
(*PFLT_GENERIC_WORKITEM_ROUTINE) (
 _In_ PFLT_GENERIC_WORKITEM FltWorkItem,
 _In_ PVOID FltObject,
 _In_opt_ PVOID Context
      );</pre>
</td>
</tr>
</table></span></div>

`QueueType`

Specifies the queue into which the work item that <i>FltWorkItem</i> points to is to be inserted. <i>QueueType</i> can be either of the following: 
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
Insert the work item into the queue from which a system thread with a real-time priority attribute  processes the work item. 

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

`Context`

Pointer to caller-defined context information to be passed as the <i>Context</i> parameter of the callback routine specified in the <i>WorkerRoutine</i> parameter. This parameter is optional.


## Return Value

<b>FltQueueGenericWorkItem</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following: 
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_DELETING_OBJECT</b></dt>
</dl>
</td>
<td width="60%">
The minifilter driver is being unloaded. This is an error code. 

</td>
</tr>
</table>

## Remarks

<b>FltQueueGenericWorkItem</b> inserts a work item that is not associated with a specific I/O operation into a system work queue. The specified <i>WorkerRoutine</i> callback routine is called in the context of a system thread, at IRQL PASSIVE_LEVEL. 

To allocate a work item, call <a href="..\fltkernel\nf-fltkernel-fltallocategenericworkitem.md">FltAllocateGenericWorkItem</a>. 

To free the work item when it is no longer needed, call <a href="..\fltkernel\nf-fltkernel-fltfreegenericworkitem.md">FltFreeGenericWorkItem</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | fltkernel.h (include Fltkernel.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** |  |

## See Also

<a href="..\fltkernel\nf-fltkernel-fltfreegenericworkitem.md">FltFreeGenericWorkItem</a>

<a href="..\fltkernel\nf-fltkernel-fltallocategenericworkitem.md">FltAllocateGenericWorkItem</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltQueueGenericWorkItem function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>