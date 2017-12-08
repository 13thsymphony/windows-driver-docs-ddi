---
UID: NC.wdfinterrupt.EVT_WDF_INTERRUPT_WORKITEM
title: EVT_WDF_INTERRUPT_WORKITEM
author: windows-driver-content
description: A driver's EvtInterruptWorkItem event callback function processes interrupt information that the driver's EvtInterruptIsr callback function has stored.
old-location: wdf\evtinterruptworkitem.htm
old-project: wdf
ms.assetid: 1A473A08-EA23-4DFE-8B58-EBB4AC977891
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
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.alt-api: EvtInterruptWorkItem
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
req.irql: PASSIVE_LEVEL
req.product: Windows 10 or later.
---

# EVT_WDF_INTERRUPT_WORKITEM callback



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
A driver's <i>EvtInterruptWorkItem</i> event callback function processes interrupt information that the driver's <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function has stored.


## -prototype

````
EVT_WDF_INTERRUPT_WORKITEM EvtInterruptWorkItem;

VOID EvtInterruptWorkItem(
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
None

## -remarks
The <i>EvtInterruptWorkItem</i> callback function runs at IRQL = PASSIVE_LEVEL.

To register an <i>EvtInterruptWorkItem</i> callback function, your driver must place the callback function's address in a <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure before calling <a href="wdf.wdfinterruptcreate">WdfInterruptCreate</a>.

Most drivers use a single <i>EvtInterruptWorkItem</i> callback function for each type of interrupt. 


To schedule execution of an <i>EvtInterruptWorkItem</i> callback function, the driver must call <a href="wdf.wdfinterruptqueueworkitemforisr">WdfInterruptQueueWorkItemForIsr</a> from within the <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_isr.md">EvtInterruptIsr</a> callback function.

If your driver creates multiple framework interrupt objects for each device, you might consider using a separate <i>EvtInterruptWorkItem</i> callback for each interrupt.


Drivers that implement either DIRQL  interrupt handling or passive level interrupt handling can queue an <i>EvtInterruptWorkItem</i> callback.

 A driver cannot queue both an <a href="..\wdfinterrupt\nc-wdfinterrupt-evt_wdf_interrupt_dpc.md">EvtInterruptDpc</a> and a <i>EvtInterruptWorkItem</i> callback.

If the driver has set the <b>AutomaticSerialization</b> member to TRUE in the interrupt's <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> structure, the framework  synchronizes execution of the interrupt object's <i>EvtInterruptWorkItem</i> callback function with callback functions from other objects that are underneath the interrupt's parent object.  For information about callback synchronization locks, see <a href="wdf.using_framework_locks">Using Framework Locks</a>.

 In general, if the driver needs to acquire the interrupt object's passive lock from within <i>EvtInterruptWorkItem</i>, the driver should set the <b>AutomaticSerialization</b> member of <a href="wdf.wdf_interrupt_config">WDF_INTERRUPT_CONFIG</a> to FALSE and then call <a href="wdf.wdfinterruptacquirelock">WdfInterruptAcquireLock</a> from within <i>EvtInterruptWorkItem</i>.

If  <b>AutomaticSerialization</b> is set to TRUE, a driver's <i>EvtInterruptWorkItem</i>  callback function should not call any of the following methods:

For more information about handling interrupts in framework-based drivers, see <a href="wdf.handling_hardware_interrupts">Handling Hardware Interrupts</a>.

To define an <i>EvtInterruptWorkItem</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtInterruptWorkItem</i> callback function that is named <i>MyInterruptWorkItem</i>, use the <b>EVT_WDF_INTERRUPT_WORKITEM</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_INTERRUPT_WORKITEM</b> function type is defined in the Wdfinterrupt.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_INTERRUPT_WORKITEM</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

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
1.11
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
PASSIVE_LEVEL
</td>
</tr>
</table>