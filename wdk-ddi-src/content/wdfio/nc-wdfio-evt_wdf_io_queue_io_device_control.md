---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL
title: EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL
author: windows-driver-content
description: A driver's EvtIoDeviceControl event callback function processes a specified device I/O control request.
old-location: wdf\evtiodevicecontrol.htm
old-project: wdf
ms.assetid: 3e3c4c53-e557-4bd1-8b7d-be59dde4b9ce
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtiodevicecontrol, EvtIoDeviceControl callback function, EvtIoDeviceControl, EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL, EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL, wdfio/EvtIoDeviceControl, DFQueueObjectRef_90eafb20-dd9c-49ca-b435-fdee9b13e4e1.xml, kmdf.evtiodevicecontrol
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdfio.h
apiname:
-	EvtIoDeviceControl
product: Windows
targetos: Windows
req.typenames: WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
req.product: Windows 10 or later.
---


# EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoDeviceControl</i> event callback function processes a specified device I/O control request.

## Syntax

```
EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL EvtWdfIoQueueIoDeviceControl;

void EvtWdfIoQueueIoDeviceControl(
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

The driver-defined or system-defined I/O control code (IOCTL) that is associated with the request.


## Return Value

None

## Remarks

A driver registers an <i>EvtIoDeviceControl</i> callback function when it calls <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoDeviceControl</i> callback function for a device's I/O queue, the callback function receives every I/O control request (<a href="https://msdn.microsoft.com/library/windows/hardware/ff548649">IRP_MJ_DEVICE_CONTROL</a>) from the queue. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoDeviceControl</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://msdn.microsoft.com/90b1cc51-da40-45c1-9d6c-57f637f474d9">Processing I/O Requests</a>.

Drivers receive I/O control requests when a user application calls <a href="https://msdn.microsoft.com/1d35c087-6672-4fc6-baa1-a886dd9d3878">DeviceIoControl</a> (described in Microsoft Windows SDK documentation) or when another driver creates a request by calling either <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a> or <a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforioctl.md">WdfIoTargetFormatRequestForIoctl</a>.

The type of operation to be performed depends on the value of the <i>IoControlCode</i> parameter. You must determine the set of <i>IoControlCode</i> values that applications and other drivers can send to your driver. For more information about IOCTLs, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff565406">Using I/O Control Codes</a>.

Most device I/O control operations require an input buffer, an output buffer, or both. For information about how the driver can access a request's buffers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

The techniques that your driver can use to access the request's input and output buffers (if they exist) depend on the <i>TransferType</i> field of the IOCTL. The value of the IOCTL's <i>TransferType</i> field can be METHOD_BUFFERED, METHOD_DIRECT_IN, METHOD_DIRECT_OUT, or METHOD_NEITHER. For more information about the <i>TransferType</i> field, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff543023">Defining I/O Control Codes</a>.

The <i>EvtIoDeviceControl</i> callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoDeviceControl</i> callback function should not call the following queue object methods:<dl>
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

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfio.h (include Wdf.h) |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |

## See Also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetformatrequestforioctl.md">WdfIoTargetFormatRequestForIoctl</a>

<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_internal_device_control.md">EvtIoInternalDeviceControl</a>

<a href="..\wdfiotarget\nf-wdfiotarget-wdfiotargetsendioctlsynchronously.md">WdfIoTargetSendIoctlSynchronously</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_QUEUE_IO_DEVICE_CONTROL callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>