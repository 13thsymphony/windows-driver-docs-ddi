---
UID: NC.wdfio.EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS
title: EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS
author: windows-driver-content
description: A driver's EvtIoWdmIrpForForwardProgress callback function examines an I/O request packet (IRP) and determines whether to use a reserved request object to process the I/O request or to fail the I/O request.
old-location: wdf\evtiowdmirpforforwardprogress.htm
old-project: wdf
ms.assetid: 71974802-954d-4856-a32b-1dcc45c36ba5
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.9
req.umdf-ver: 
req.alt-api: EvtIoWdmIrpForForwardProgress
req.alt-loc: Wdfio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS callback



## -description
<p class="CCE_Message">[Applies to KMDF only]

A driver's <i>EvtIoWdmIrpForForwardProgress</i> callback function examines an I/O request packet (IRP) and determines whether to use a reserved request object to process the I/O request or to fail the I/O request.



## -prototype

````
EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS EvtIoWdmIrpForForwardProgress;

WDF_IO_FORWARD_PROGRESS_ACTION EvtIoWdmIrpForForwardProgress(
  _In_ WDFQUEUE Queue,
  _In_ PIRP     Irp
)
{ ... }
````


## -parameters

### -param Queue [in]

A handle to an I/O queue object.


### -param Irp [in]

A pointer to an IRP structure.


## -returns
The <i>EvtIoWdmIrpForForwardProgress</i> callback function must return a <a href="wdf.wdf_io_forward_progress_action">WDF_IO_FORWARD_PROGRESS_ACTION</a>-typed value.


## -remarks
A driver can register an <i>EvtIoWdmIrpForForwardProgress</i> callback function when it calls <a href="wdf.wdfioqueueassignforwardprogresspolicy">WdfIoQueueAssignForwardProgressPolicy</a>.

If your driver registers an <i>EvtIoWdmIrpForForwardProgress</i> callback function, the framework calls the function if all of the following conditions exist:

The framework has received a I/O request packet (<a href="kernel.irp">IRP</a>) that the I/O manager is sending to the driver.

The framework has attempted to create a request object for the IRP, but the attempt failed.

The driver has enabled guaranteed forward progress for the I/O queue that should receive the request object, with the <a href="wdf.wdf_io_forward_progress_reserved_policy">policy type</a> set to <b>WdfIoForwardProgressReservedPolicyUseExamine</b>.

The framework passes the IRP to the <i>EvtIoWdmIrpForForwardProgress</i> callback function. The callback function must examine the IRP and determine whether the framework should use one of its reserved request objects for the IRP or (if the IRP is not important when the computer's available memory is low) fail the I/O request without delivering it to the driver. The callback function's return value specifies the action that the framework should take.

For more information about the <i>EvtIoWdmIrpForForwardProgress</i> callback function, see <a href="wdf.guaranteeing_forward_progress_of_i_o_operations">Guaranteeing Forward Progress of I/O Operations</a>.

This callback function can be called at IRQL &lt;= DISPATCH_LEVEL. If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.

To define an <i>EvtIoWdmIrpForForwardProgress</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoWdmIrpForForwardProgress</i> callback function that is named <i>MyIoForwardExamineIrpForForwardProgress</i>, use the <b>EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


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
Minimum KMDF version

</th>
<td width="70%">
1.9

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL (see Remarks section)

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_request_resources.md">EvtIoAllocateRequestResources</a>
</dt>
<dt>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_allocate_resources_for_reserved_request.md">EvtIoAllocateResourcesForReservedRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_WDM_IRP_FOR_FORWARD_PROGRESS callback function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

