---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_RESUME
title: EVT_WDF_IO_QUEUE_IO_RESUME function
author: windows-driver-content
description: A driver's EvtIoResume event callback function resumes processing a specified I/O request after the underlying device returns to its working (D0) power state.
old-location: wdf\evtioresume.htm
old-project: wdf
ms.assetid: 97731224-bf08-4578-958e-729acbb5a628
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: EVT_WDF_IO_QUEUE_IO_RESUME
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: EvtIoResume
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
req.typenames: *PWDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO
req.product: Windows 10 or later.
---

# EVT_WDF_IO_QUEUE_IO_RESUME function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoResume</i> event callback function resumes processing a specified I/O request after the underlying device returns to its working (D0) power state.



## -syntax

````
EVT_WDF_IO_QUEUE_IO_RESUME EvtIoResume;

VOID EvtIoResume(
  _In_ WDFQUEUE   Queue,
  _In_ WDFREQUEST Request
)
{ ... }
````


## -parameters

### -param Queue [in]

A handle to the framework queue object that is associated with the I/O request.


### -param Request [in]

A handle to a framework request object.


## -returns
None


## -remarks
A driver registers an <i>EvtIoResume</i> callback function when it calls the <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a> method. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://msdn.microsoft.com/03b09c94-6b72-4234-b21f-203f93b7a2e8">Creating I/O Queues</a>.

A driver registers <i>EvtIoResume</i> only for use with a power-managed queue.

The framework calls the driver's <i>EvtIoResume</i> callback function only if the driver's <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function previously called <a href="..\wdfrequest\nf-wdfrequest-wdfrequeststopacknowledge.md">WdfRequestStopAcknowledge</a> with the <i>Requeue</i> parameter set to <b>FALSE</b>.

For more information about the <i>EvtIoResume</i> callback function, see <a href="https://msdn.microsoft.com/271d55ef-d82e-4ffd-bf41-a602c42c3f0e">Using Power-Managed I/O Queues</a>.

This callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>. You should not make this callback function <a href="wdf.creating_pageable_code_in_a_kmdf_driver">pageable</a>.

To define an <i>EvtIoResume</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoResume</i> callback function that is named <i>MyIoResume</i>, use the <b>EVT_WDF_IO_QUEUE_IO_RESUME</b> type as shown in this code example:

Then, implement your callback function as follows:

The <b>EVT_WDF_IO_QUEUE_IO_RESUME</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_RESUME</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>
</dt>
<dt>
<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_QUEUE_IO_RESUME callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

