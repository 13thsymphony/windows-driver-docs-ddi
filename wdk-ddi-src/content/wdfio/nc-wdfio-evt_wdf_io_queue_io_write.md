---
UID : NC:wdfio.EVT_WDF_IO_QUEUE_IO_WRITE
title : EVT_WDF_IO_QUEUE_IO_WRITE
author : windows-driver-content
description : A driver's EvtIoWrite event callback function processes a specified write request.
old-location : wdf\evtiowrite.htm
old-project : wdf
ms.assetid : 5a0fa3b4-d020-4664-afa4-352573d4f079
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdf.evtiowrite, EvtIoWrite callback function, EvtIoWrite, EVT_WDF_IO_QUEUE_IO_WRITE, EVT_WDF_IO_QUEUE_IO_WRITE, wdfio/EvtIoWrite, DFQueueObjectRef_c98601af-48d0-4fc1-9947-b94c50f7a994.xml, kmdf.evtiowrite
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdfio.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL (see Remarks section)"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_INTERRUPT_INFO, *PWDF_INTERRUPT_INFO
req.product : Windows 10 or later.
---


# EVT_WDF_IO_QUEUE_IO_WRITE function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoWrite</i> event callback function processes a specified write request.

## Syntax

```
EVT_WDF_IO_QUEUE_IO_WRITE EvtWdfIoQueueIoWrite;

void EvtWdfIoQueueIoWrite(
  WDFQUEUE Queue,
  WDFREQUEST Request,
  size_t Length
)
{...}
```

## Parameters

`Queue`

A handle to the framework queue object that is associated with the I/O request.

`Request`

A handle to a framework request object.

`Length`

The number of bytes to be written.


## Return Value

None

## Remarks

A driver registers an <i>EvtIoWrite</i> callback function when it calls <a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>. For more information about calling <b>WdfIoQueueCreate</b>, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/creating-i-o-queues">Creating I/O Queues</a>.

If a driver has registered an <i>EvtIoWrite</i> callback function for a device's I/O queue, the callback function receives every write request from the queue. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">Request Handlers</a>.

The <i>EvtIoWrite</i> callback function must process each received I/O request in some manner. For more information, see <a href="https://msdn.microsoft.com/90b1cc51-da40-45c1-9d6c-57f637f474d9">Processing I/O Requests</a>.

Write requests require an input buffer, which contains data that the driver receives. For information about how the driver can access a write request's buffer, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/accessing-data-buffers-in-wdf-drivers">Accessing Data Buffers in Framework-Based Drivers</a>.

This callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.

For more information about IRQL levels for request handlers, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-automatic-synchronization">Using Automatic Synchronization</a>.

A driver's <i>EvtIoWrite</i> callback function should not call the following queue object methods:<dl>
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

<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_default.md">EvtIoDefault</a>

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuecreate.md">WdfIoQueueCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_QUEUE_IO_WRITE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>