---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL
title: EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL
author: windows-driver-content
description: A driver's EvtIoInternalDeviceControl event callback function processes an I/O request that contains an internal device I/O control code (IOCTL).
old-location: wdf\evtiointernaldevicecontrol.htm
old-project: wdf
ms.assetid: 268d2323-57a3-4674-90e6-d7142804175b
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: DFQueueObjectRef_6b883c59-a84e-4735-8dec-2b0123b0d61f.xml, EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL, EvtIoInternalDeviceControl, EvtIoInternalDeviceControl callback function, kmdf.evtiointernaldevicecontrol, wdf.evtiointernaldevicecontrol, wdfio/EvtIoInternalDeviceControl
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Wdfio.h
api_name:
-	EvtIoInternalDeviceControl
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
req.product: Windows 10 or later.
---


# EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL callback function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoInternalDeviceControl</i> event callback function processes an I/O request that contains an internal device I/O control code (IOCTL).

## Syntax

```
EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL EvtWdfIoQueueIoInternalDeviceControl;

void EvtWdfIoQueueIoInternalDeviceControl(
  WDFQUEUE Queue,
  WDFREQUEST Request,
  size_t OutputBufferLength,
  size_t InputBufferLength,
  ULONG IoControlCode
)
{...}
```

## Parameters

`Queue`

A handle to the framework queue object that is associated with the I/O request.

`Request`

A handle to a framework request object.

`OutputBufferLength`

The length, in bytes, of the request's output buffer, if an output buffer is available.

`InputBufferLength`

The length, in bytes, of the request's input buffer, if an input buffer is available.

`IoControlCode`

The driver-defined or system-defined IOCTL that is associated with the request.


## Return Value

None

## Remarks

A driver registers an <i>EvtIoInternalDeviceControl</i> callback function when it calls the <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a> method. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoInternalDeviceControl</i> callback function for a device's I/O queue, the callback function receives every internal I/O control request (<a href="https://msdn.microsoft.com/library/windows/hardware/ff550766">IRP_MJ_INTERNAL_DEVICE_CONTROL</a>) from the queue. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoInternalDeviceControl</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://msdn.microsoft.com/90b1cc51-da40-45c1-9d6c-57f637f474d9">Processing I/O Requests</a>.

Drivers receive internal I/O control requests when another driver creates a request by calling either  <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforinternalioctl.md">WdfIoTargetFormatRequestForInternalIoctl</a>.

The type of operation to be performed depends on the value of the <i>IoControlCode</i> parameter. You must determine the set of <i>IoControlCode</i> values that applications and other drivers can send to your driver. For more information about IOCTLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.

Most internal I/O control operations require an input buffer, an output buffer, or both. For information about how the driver can access a request's buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

The techniques that your driver can use to access the request's input and output buffers (if they exist) depend on the <i>TransferType</i> field of the IOCTL. The value of the IOCTL's <i>TransferType</i> field can be METHOD_BUFFERED, METHOD_DIRECT_IN, METHOD_DIRECT_OUT, or METHOD_NEITHER. For more information about the <i>TransferType</i> field, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543023">Defining I/O Control Codes</a>.

The <i>EvtIoInternalDeviceControl</i> callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>. (If your driver is at the top of its driver stack, the callback function is called at IRQL = PASSIVE_LEVEL.)

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoInternalDeviceControl</i> callback function should not call the following queue object methods:<dl>
<dd>
<a href="..\wdfio\nf-wdfio-wdfioqueuedrainsynchronously.md">WdfIoQueueDrainSynchronously</a>
</dd>
<dd>
<a href="..\wdfio\nf-wdfio-wdfioqueuepurgesynchronously.md">WdfIoQueuePurgeSynchronously</a>
</dd>
<dd>
<a href="..\wdfio\nf-wdfio-wdfioqueuestopsynchronously.md">WdfIoQueueStopSynchronously</a>
</dd>
</dl>



#### Examples

To define an <i>EvtIoInternalDeviceControl</i> callback function, you must first provide a function declaration that identifies the type of callback function you’re defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it’s a requirement for writing drivers for the Windows operating system.

For example, to define an <i>EvtIoInternalDeviceControl</i> callback function that is named <i>MyIoInternalDeviceControl</i>, use the <b>EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL  MyIoInternalDeviceControl;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyIoInternalDeviceControl (
    WDFQUEUE  Queue,
    WDFREQUEST  Request,
    size_t  OutputBufferLength,
    size_t  InputBufferLength,
    ULONG  IoControlCode
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL</b> function type is defined in the Wdfio.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL</b> function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For information about _Use_decl_annotations_, see <a href="https://msdn.microsoft.com/en-US/library/c0aa268d-6fa3-4ced-a8c6-f7652b152e61">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfio.h (include Wdf.h) |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |

## See Also

<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_device_control.md">EvtIoDeviceControl</a>



<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendinternalioctlsynchronously.md">WdfIoTargetSendInternalIoctlSynchronously</a>



<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforinternalioctl.md">WdfIoTargetFormatRequestForInternalIoctl</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_QUEUE_IO_INTERNAL_DEVICE_CONTROL callback function%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>