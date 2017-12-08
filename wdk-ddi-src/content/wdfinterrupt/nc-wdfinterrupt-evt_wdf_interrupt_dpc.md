---
UID: NC.wdfinterrupt.EVT_WDF_INTERRUPT_DPC
title: EVT_WDF_INTERRUPT_DPC
author: windows-driver-content
description: A driver's EvtInterruptDpc event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored.
old-location: wdf\evtinterruptdpc.htm
old-project: wdf
ms.assetid: d2d505e0-aeac-4871-8c60-d026b2833043
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_COINSTALLER_INSTALL_OPTIONS, WDF_COINSTALLER_INSTALL_OPTIONS, *PWDF_COINSTALLER_INSTALL_OPTIONS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfinterrupt.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtInterruptDpc
req.alt-loc: Wdfinterrupt.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: (See Remarks section.)
req.product: Windows 10 or later.
---

# EVT_WDF_INTERRUPT_DPC callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
A driver's <i>EvtInterruptDpc</i> event callback function processes interrupt information that the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function has stored.


## -prototype

````
EVT_WDF_INTERRUPT_DPC EvtInterruptDpc;

void EvtInterruptDpc(
  _In_ WDFINTERRUPT Interrupt,
  _In_ WDFOBJECT    AssociatedObject
)
{ ... }
````


## -parameters

### -param Interrupt [in]

A handle to a framework interrupt object.

### -param AssociatedObject [in]

A handle to the framework device object that the driver passed to <a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a>.

## -returns
This callback function does not return a value.

## -remarks
To register an <i>EvtInterruptDpc</i> callback function, your driver must place the callback function's address in a <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a>.

Drivers typically <a href="wdf.completing_i_o_requests">complete I/O requests</a> in their <i>EvtInterruptDpc</i> callback functions.

The <i>EvtInterruptDpc</i> callback function executes at DISPATCH_LEVEL and must not access <a href="https://msdn.microsoft.com/0b3c1e00-2416-4534-9934-bb05f91c7482">pageable</a> code. If an <i>EvtInterruptDpc</i> callback function must perform operations at IRQL = PASSIVE_LEVEL, it can <a href="wdf.using_framework_work_items">use framework work items</a>. 

In KMDF version 1.11 and later, your driver can support <a href="wdf.supporting_passive_level_interrupts">passive-level interrupts</a> and provide either an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_workitem.md">EvtInterruptWorkItem</a> or an <i>EvtInterruptDpc</i> callback function. If your driver supports passive-level interrupts and provides an <i>EvtInterruptDpc</i> callback function, the driver cannot acquire the passive-level interrupt lock from within the callback.

Most drivers use a single <i>EvtInterruptDpc</i> callback function for each type of interrupt. If your driver creates multiple <a href="wdf.framework_queue_objects">framework queue objects</a> for each device, you might consider using a separate <a href="wdf.wdf_dpc_object_reference">DPC object</a> and <a href="wdf.evtdpcfunc">EvtDpcFunc</a> callback function for each queue.

To schedule execution of an <i>EvtInterruptDpc</i> callback function, the driver must call <a href="wdf.wdfinterruptqueuedpcforisr">WdfInterruptQueueDpcForIsr</a> from within the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function.

When a driver schedules the execution of an <i>EvtInterruptDpc</i> callback function, the system adds a DPC object to the system's DPC queue. If the system is not executing higher-priority tasks, it removes the object from the queue and calls the <i>EvtInterruptDpc</i> callback function. 

The system does not add the DPC object to the DPC queue if the object is already queued. An <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function might be called several times before the system calls the <i>EvtInterruptDpc</i> callback function. Therefore, the <i>EvtInterruptDpc</i> callback function must be able to process information from several interrupts, and it must process all interrupts that have occurred since the last time it was called.

Typically, it is necessary to synchronize the execution of a driver's <i>EvtInterruptDpc</i> callback function with the execution of other callback functions. For more information, see <a href="wdf.synchronizing_interrupt_code">Synchronizing Interrupt Code</a>.

For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.

To define an <i>EvtInterruptDpc</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtInterruptDpc</i> callback function that is named <i>MyInterrruptDpc</i>, use the <b>EVT_WDF_INTERRUPT_DPC</b> type as shown in this code example:

Then, implement your callback function as follows.

The <b>EVT_WDF_INTERRUPT_DPC</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_INTERRUPT_DPC</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

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
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wdfinterrupt.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
(See Remarks section.)
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a>
</dt>
<dt>
<a href="wdf.wdfinterruptqueuedpcforisr">WdfInterruptQueueDpcForIsr</a>
</dt>
<dt>
<a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a>
</dt>
<dt>
<a href="wdf.evtdpcfunc">EvtDpcFunc</a>
</dt>
<dt>
<a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_INTERRUPT_DPC callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
