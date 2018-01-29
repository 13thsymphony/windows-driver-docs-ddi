---
UID : NF:wdfio.WdfIoQueueDrain
title : WdfIoQueueDrain function
author : windows-driver-content
description : The WdfIoQueueDrain method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed.
old-location : wdf\wdfioqueuedrain.htm
old-project : wdf
ms.assetid : 376579c6-545d-4f5a-8ba4-0046c0b2b755
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfio/WdfIoQueueDrain, wdf.wdfioqueuedrain, WdfIoQueueDrain method, WdfIoQueueDrain, kmdf.wdfioqueuedrain, PFN_WDFIOQUEUEDRAIN, DFQueueObjectRef_39ca90c2-1fc9-4f1c-b05f-d46f668a3cd1.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfio.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : ChangeQueueState, DriverCreate, EvtSurpriseRemoveNoSuspendQueue, KmdfIrql, KmdfIrql2, NoCancelFromEvtSurpriseRemove
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_IO_QUEUE_STATE
req.product : Windows 10 or later.
---


# WdfIoQueueDrain function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueDrain</b> method causes the framework to stop queuing I/O requests to an I/O queue, while allowing already-queued requests to be delivered and processed.

## Syntax

````
VOID WdfIoQueueDrain(
  _In_     WDFQUEUE               Queue,
  _In_opt_ PFN_WDF_IO_QUEUE_STATE DrainComplete,
  _In_opt_ WDFCONTEXT             Context
);
````

## Parameters

`Queue`

A handle to a framework queue object.

`DrainComplete`

A pointer to a driver-supplied <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.

`Context`

An untyped pointer to driver-supplied context information that the framework passes to the <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

After a driver calls <b>WdfIoQueueDrain</b>, the framework stops adding I/O requests to the specified queue. If the framework receives additional requests for the queue, it completes them with a completion status value of STATUS_INVALID_DEVICE_STATE.

If the driver supplies an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled.

The driver should not call another method that changes queue state, such as <a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a> or <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>, before the framework has called <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a>.

If a driver specifies <b>NULL</b> for <i>DrainComplete</i>, the driver can call another state changing operation before requests are completed.

As a best practice, you should only call <b>WdfIoQueueDrain</b> when you are certain that the queue's pending I/O requests will complete in a timely fashion. Otherwise, use <a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>. For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.

After a driver has drained an I/O queue, it can restart the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfio.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | ChangeQueueState, DriverCreate, EvtSurpriseRemoveNoSuspendQueue, KmdfIrql, KmdfIrql2, NoCancelFromEvtSurpriseRemove |

## See Also

<a href="..\wdfio\nf-wdfio-wdfioqueuedrainsynchronously.md">WdfIoQueueDrainSynchronously</a>

<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueDrain method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>