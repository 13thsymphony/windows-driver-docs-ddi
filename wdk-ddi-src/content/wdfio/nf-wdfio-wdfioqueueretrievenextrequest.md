---
UID: NF.wdfio.WdfIoQueueRetrieveNextRequest
title: WdfIoQueueRetrieveNextRequest function
author: windows-driver-content
description: The WdfIoQueueRetrieveNextRequest method retrieves the next available I/O request from a specified I/O queue.
old-location: wdf\wdfioqueueretrievenextrequest.htm
old-project: wdf
ms.assetid: 1cde2e20-5ce6-4c5b-b40c-0b04da76980c
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: WdfIoQueueRetrieveNextRequest
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
req.alt-api: WdfIoQueueRetrieveNextRequest
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DoubleCompletion, DriverCreate, KmdfIrql, KmdfIrql2, wdfioqueueretrievenextrequest
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfIoQueueRetrieveNextRequest function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueRetrieveNextRequest</b> method retrieves the next available I/O request from a specified I/O queue. 



## -syntax

````
NTSTATUS WdfIoQueueRetrieveNextRequest(
  _In_  WDFQUEUE   Queue,
  _Out_ WDFREQUEST *OutRequest
);
````


## -parameters

### -param Queue [in]

A handle to a framework queue object.


### -param OutRequest [out]

A pointer to a location that receives a handle to a framework request object. If the queue is empty or the last request has been retrieved, this parameter receives <b>NULL</b>.


## -returns
<b>WdfIoQueueRetrieveNextRequest</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>The driver supplied an invalid handle.
<dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl>The framework reached the end of the I/O queue.
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>The specified I/O queue is configured for the parallel dispatching method.
<dl>
<dt><b>STATUS_WDF_PAUSED</b></dt>
</dl>The specified I/O queue is <a href="wdf.using_power_managed_i_o_queues">power-managed</a> and its device is in a low-power state, or the specified queue is stopped.

 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
If a driver configures an I/O queue for manual dispatching of I/O requests, the driver typically calls <b>WdfIoQueueRetrieveNextRequest</b> to obtain requests from the queue. A driver that has configured an I/O queue for sequential dispatching might also call <b>WdfIoQueueRetrieveNextRequest</b>. For more information about using <b>WdfIoQueueRetrieveNextRequest</b> with the manual or sequential dispatching methods, see <a href="wdf.dispatching_methods_for_i_o_requests">Dispatching Methods for I/O Requests</a>. 

After calling <b>WdfIoQueueRetrieveNextRequest</b> to obtain an I/O request, the driver <a href="wdf.request_ownership">owns</a> the request and must <a href="wdf.accessing_data_buffers_in_kmdf_drivers">process the I/O request</a> in some manner.

For more information about the <b>WdfIoQueueRetrieveNextRequest</b> method, see <a href="wdf.managing_i_o_queues">Managing I/O Queues</a>.

The following code example obtains a handle to the next request object that is contained in a device's I/O queue.


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
<a href="devtest.kmdf_doublecompletion">DoubleCompletion</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_wdfioqueueretrievenextrequest">wdfioqueueretrievenextrequest</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfioqueueretrievefoundrequest">WdfIoQueueRetrieveFoundRequest</a>
</dt>
<dt>
<a href="wdf.wdfioqueueretrieverequestbyfileobject">WdfIoQueueRetrieveRequestByFileObject</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueRetrieveNextRequest method%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

