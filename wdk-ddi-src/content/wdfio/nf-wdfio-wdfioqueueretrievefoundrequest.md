---
UID: NF.wdfio.WdfIoQueueRetrieveFoundRequest
title: WdfIoQueueRetrieveFoundRequest
author: windows-driver-content
description: The WdfIoQueueRetrieveFoundRequest method delivers a specified request to the driver, so that the driver can process the request.
old-location: wdf\wdfioqueueretrievefoundrequest.htm
old-project: wdf
ms.assetid: 34447879-1a2e-45de-b754-121a5956330a
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WdfIoQueueRetrieveFoundRequest
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
req.alt-api: WdfIoQueueRetrieveFoundRequest
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DoubleCompletion, DriverCreate, KmdfIrql, KmdfIrql2, wdfioqueuefindrequestfailed, wdfioqueueretrievefoundrequest
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); 
WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WdfIoQueueRetrieveFoundRequest function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfIoQueueRetrieveFoundRequest</b> method delivers a specified request to the driver, so that the driver can process the request.</p>


## -syntax

````
NTSTATUS WdfIoQueueRetrieveFoundRequest(
  _In_  WDFQUEUE   Queue,
  _In_  WDFREQUEST FoundRequest,
  _Out_ WDFREQUEST *OutRequest
);
````


## -parameters
<dl>

### -param <i>Queue</i> [in]

<dd>
<p>A handle to a framework queue object.</p>
</dd>

### -param <i>FoundRequest</i> [in]

<dd>
<p>A handle to a framework request object that was obtained by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>.</p>
</dd>

### -param <i>OutRequest</i> [out]

<dd>
<p>A pointer to a location that receives a handle to a framework request object. The driver must use this handle when processing the request.</p>
</dd>
</dl>

## -returns
<p><b>WdfIoQueueRetrieveFoundRequest</b>  returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>The driver supplied an invalid handle.</p><dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl><p>The request that is identified by the <i>FoundRequest</i> parameter cannot be found in the I/O queue.</p><dl>
<dt><b>STATUS_NO_MORE_ENTRIES</b></dt>
</dl><p>The framework reached the end of the I/O queue without finding a request that matches the search criteria.</p>

<p> </p>

<p>This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.</p>

<p>A bug check occurs if the driver supplies an invalid object handle.

</p>

## -remarks
<p>After calling <b>WdfIoQueueRetrieveFoundRequest</b> to obtain an I/O request, the driver <a href="wdf.request_ownership">owns</a> the request and must <a href="wdf.accessing_data_buffers_in_kmdf_drivers">process the I/O request</a> in some manner.</p>

<p>Before calling <b>WdfIoQueueRetrieveFoundRequest</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>, which retrieves a handle that the driver can use as the <i>FoundRequest</i> parameter to <b>WdfIoQueueRetrieveFoundRequest</b>.</p>

<p>If your driver was built with KMDF version 1.11 or later, the driver can call <b>WdfIoQueueRetrieveFoundRequest</b> without first calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>. In this case, the driver must ensure that the request object is still valid and in the queue.</p>

<p>If a call to <b>WdfIoQueueRetrieveFoundRequest</b> returns STATUS_NOT_FOUND, a request that was previously in the queue has been removed. The request might have been canceled. </p>

<p>For more information about the <b>WdfIoQueueRetrieveFoundRequest</b> method, see <a href="wdf.managing_i_o_queues">Managing I/O Queues</a>.</p>

<p>For a code example that uses <b>WdfIoQueueRetrieveFoundRequest</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>.</p>

<p>After calling <b>WdfIoQueueRetrieveFoundRequest</b> to obtain an I/O request, the driver <a href="wdf.request_ownership">owns</a> the request and must <a href="wdf.accessing_data_buffers_in_kmdf_drivers">process the I/O request</a> in some manner.</p>

<p>Before calling <b>WdfIoQueueRetrieveFoundRequest</b>, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>, which retrieves a handle that the driver can use as the <i>FoundRequest</i> parameter to <b>WdfIoQueueRetrieveFoundRequest</b>.</p>

<p>If your driver was built with KMDF version 1.11 or later, the driver can call <b>WdfIoQueueRetrieveFoundRequest</b> without first calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>. In this case, the driver must ensure that the request object is still valid and in the queue.</p>

<p>If a call to <b>WdfIoQueueRetrieveFoundRequest</b> returns STATUS_NOT_FOUND, a request that was previously in the queue has been removed. The request might have been canceled. </p>

<p>For more information about the <b>WdfIoQueueRetrieveFoundRequest</b> method, see <a href="wdf.managing_i_o_queues">Managing I/O Queues</a>.</p>

<p>For a code example that uses <b>WdfIoQueueRetrieveFoundRequest</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Target platform</p>
</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum KMDF version</p>
</th>
<td width="70%">
<p>1.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum UMDF version</p>
</th>
<td width="70%">
<p>2.0</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>Library</p>
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
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff819059">DoubleCompletion</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975098">wdfioqueuefindrequestfailed</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975099">wdfioqueueretrievefoundrequest</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff547415">WdfIoQueueFindRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/hh975100">WdfIoQueueRetrieveNextRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff548470">WdfIoQueueRetrieveRequestByFileObject</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueRetrieveFoundRequest method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
