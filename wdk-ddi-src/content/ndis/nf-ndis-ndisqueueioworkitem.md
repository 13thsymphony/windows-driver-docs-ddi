---
UID: NF:ndis.NdisQueueIoWorkItem
title: NdisQueueIoWorkItem function
author: windows-driver-content
description: NDIS drivers call the NdisQueueIoWorkItem function to queue a work item.
old-location: netvista\ndisqueueioworkitem.htm
old-project: netvista
ms.assetid: f5065217-a74e-41b6-bc23-59b39948a450
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: NdisQueueIoWorkItem
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NdisQueueIoWorkItem
req.alt-loc: ndis.lib,ndis.dll
req.ddi-compliance: Irql_Miscellaneous_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisQueueIoWorkItem function



## -description
NDIS drivers call the 
  <b>NdisQueueIoWorkItem</b> function to queue a work item.



## -syntax

````
VOID NdisQueueIoWorkItem(
  _In_ NDIS_HANDLE              NdisIoWorkItemHandle,
  _In_ NDIS_IO_WORKITEM_ROUTINE Routine,
  _In_ PVOID                    WorkItemContext
);
````


## -parameters

### -param NdisIoWorkItemHandle [in]

A handle to a private <a href="https://msdn.microsoft.com/library/windows/hardware/ff550679">IO_WORKITEM</a> structure that was returned by a previous call to the 
     <a href="..\ndis\nf-ndis-ndisallocateioworkitem.md">
     NdisAllocateIoWorkItem</a> function.


### -param Routine [in]

The entry point to the function that NDIS calls to process the work item. NDIS calls this routine
     in the context of a system thread. 

<div class="alert"><b>Note</b>  You must declare the function by using the <b>NDIS_IO_WORKITEM_FUNCTION</b> type (not <b>NDIS_IO_WORKITEM_ROUTINE</b>). For more
   information, see the following Examples section.</div>
<div> </div>
The routine includes the following input parameters:




### -param WorkItemContext

A pointer to the context area that the driver passed to the 
       <i>WorkItemContext</i> parameter of 
       <b>NdisQueueIoWorkItem</b>.


### -param NdisIoWorkItemHandle

A handle to a private <b>NDIS_IO_WORKITEM</b> structure that was returned by a previous call to the 
       <a href="..\ndis\nf-ndis-ndisallocateioworkitem.md">
     NdisAllocateIoWorkItem</a> function.

</dd>
</dl>

### -param WorkItemContext [in]

A pointer to a caller-supplied context area that NDIS passes through to the callback routine. 
     <i>WorkItemContext</i> can be any caller-specified data that the driver requires to manage the work
     item.


## -returns
None


## -remarks
<b>NdisQueueIoWorkItem</b> calls 
    <a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a> to queue a work item. NDIS
    work items use the 
    <b>CriticalWorkQueue</b> queue type.

The caller-supplied callback routine (NDIS_IO_WORKITEM_ROUTINE) runs in a system thread context at
    IRQL = PASSIVE_LEVEL.

This caller-supplied routine can call the 
    <a href="..\ndis\nf-ndis-ndisfreeioworkitem.md">NdisFreeIoWorkItem</a> function to reclaim
    the storage allocated for the work item.

To define a <i>Routine</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>Routine</i> function that is named "MyWorkitemRoutine", use the <b>NDIS_IO_WORKITEM_FUNCTION</b> type as shown in this code example:

Then, implement your function as follows:

The <b>NDIS_IO_WORKITEM_FUNCTION</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>NDIS_IO_WORKITEM_FUNCTION</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


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
Version

</th>
<td width="70%">
Supported in NDIS 6.0 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndis.h (include Ndis.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Ndis.lib</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547982">Irql_Miscellaneous_Function</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdm\nf-wdm-ioqueueworkitem.md">IoQueueWorkItem</a>
</dt>
<dt>
<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisallocateioworkitem.md">NdisAllocateIoWorkItem</a>
</dt>
<dt>
<a href="..\ndis\nf-ndis-ndisfreeioworkitem.md">NdisFreeIoWorkItem</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/4f966ff3-2092-495f-863f-50f079085fa6">NDIS I/O Work Items</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisQueueIoWorkItem function%20 RELEASE:%20(1/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

