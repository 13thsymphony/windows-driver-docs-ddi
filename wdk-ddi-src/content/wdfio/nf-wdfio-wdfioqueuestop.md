---
UID: NF:wdfio.WdfIoQueueStop
title: WdfIoQueueStop function
author: windows-driver-content
description: The WdfIoQueueStop method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.
old-location: wdf\wdfioqueuestop.htm
old-project: wdf
ms.assetid: 50ff8064-b28c-4b2b-89d2-bad5e503b2d6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: WdfIoQueueStop
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
req.alt-api: WdfIoQueueStop
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: ChangeQueueState, DriverCreate, EvtSurpriseRemoveNoSuspendQueue, KmdfIrql, KmdfIrql2, NoCancelFromEvtSurpriseRemove
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WdfIoQueueStop function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueStop</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests.



## -syntax

````
VOID WdfIoQueueStop(
  _In_     WDFQUEUE               Queue,
  _In_opt_ PFN_WDF_IO_QUEUE_STATE StopComplete,
  _In_opt_ WDFCONTEXT             Context
);
````


## -parameters

### -param Queue [in]

A handle to a framework queue object.


### -param StopComplete [in, optional]

A pointer to a driver-supplied <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


### -param Context [in, optional]

An untyped pointer to driver-supplied context information that the framework passes to the <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function. This parameter is optional and can be <b>NULL</b>.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
If the driver supplies an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a> callback function, the framework calls it after all requests that were delivered to the driver have been completed or canceled.

The <b>WdfIoQueueStop</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>WdfIoQueueStop</b>. For example, before calling <b>WdfIoQueueStop</b>, a driver might call <a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>WdfIoQueueStop</b> causes the framework to resume adding requests to the queue.

A driver must not call <a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a> after calling <b>WdfIoQueueStop</b> until it has restarted the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>.

For more information about the <b>WdfIoQueueStop</b> method, see <a href="https://msdn.microsoft.com/83cc87c8-7e2d-4f79-a580-0519d327e7ba">Managing I/O Queues</a>.

The following code example stops a specified I/O queue. When all requests that were delivered to the driver have been completed or canceled, it calls a driver's <b>EvtIoQueueStateStop</b> function.


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
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Library

</th>
<td width="70%">
<dl>
<dt>Wdf01000.sys (KMDF); </dt>
<dt>WUDFx02000.dll (UMDF)</dt>
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
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975067">ChangeQueueState</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975076">EvtSurpriseRemoveNoSuspendQueue</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975093">NoCancelFromEvtSurpriseRemove</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuestopsynchronously.md">WdfIoQueueStopSynchronously</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdfioqueuestart.md">WdfIoQueueStart</a>
</dt>
<dt>
<a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_state.md">EvtIoQueueState</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueStop method%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

