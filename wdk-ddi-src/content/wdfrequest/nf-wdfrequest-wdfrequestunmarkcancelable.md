---
UID: NF.wdfrequest.WdfRequestUnmarkCancelable
title: WdfRequestUnmarkCancelable
author: windows-driver-content
description: The WdfRequestUnmarkCancelable method disables cancellation of a specified I/O request.
old-location: wdf\wdfrequestunmarkcancelable.htm
old-project: wdf
ms.assetid: 91740445-e380-4798-a553-e7d502d2ce92
ms.author: windowsdriverdev
ms.date: 11/22/2017
ms.keywords: WdfRequestUnmarkCancelable
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfrequest.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WdfRequestUnmarkCancelable
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: CompleteCanceledReq, DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); 
WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.iface: 
req.product: Windows 10 or later.
---

# WdfRequestUnmarkCancelable function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]</p>
<p>The <b>WdfRequestUnmarkCancelable</b> method disables cancellation of a specified I/O request.</p>


## -syntax

````
NTSTATUS WdfRequestUnmarkCancelable(
  _In_ WDFREQUEST Request
);
````


## -parameters
<dl>

### -param <i>Request</i> [in]

<dd>
<p>A handle to a framework request object.</p>
</dd>
</dl>

## -returns
<p><b>WdfRequestUnmarkCancelable</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method might return one of the following values:</p><dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl><p>An input parameter is invalid or the request is already not cancelable.</p><dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl><p>The driver does not own the request. </p><dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl><p>The request has been canceled.</p>

<p> </p>

<p>This method might also return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.


</p>

<p>A bug check occurs if the driver supplies an invalid object handle.</p>

## -remarks
<p>A driver can call <b>WdfRequestUnmarkCancelable</b> to disable cancellation of an I/O request, if the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to enable cancellation of the request.</p>

<p>If <b>WdfRequestUnmarkCancelable</b> returns a value other than STATUS_CANCELLED, the driver's <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> callback function will not be called for the request.</p>

<p>If the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>, the driver's <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> callback function can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> with a <i>Status</i> parameter of STATUS_CANCELLED. The <i>EvtRequestCancel</i> callback function does not have to call <b>WdfRequestUnmarkCancelable</b>. If the driver calls <b>WdfRequestComplete</b> outside of its <i>EvtRequestCancel</i> callback function, the driver must first call <b>WdfRequestUnmarkCancelable</b>.</p>

<p>However, the driver must not call <b>WdfRequestUnmarkCancelable</b> after <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>. In the following Example section, the example stores a local copy of the request handle and then clears it when the <i>EvtRequestCancel</i> callback function calls <b>WdfRequestComplete</b>. The driver does not call <b>WdfRequestUnmarkCancelable</b> if the local copy of the request handle has been cleared. This example uses the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>  to synchronize the callback functions.</p>

<p>Note that calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> to add an additional reference to the request object does <i>not</i> enable your driver to call <b>WdfRequestUnmarkCancelable</b> after the driver's <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> callback function calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>. </p>

<p>If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, and then <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> completes the request, the driver must not subsequently use the request object.</p>

<p>If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, the driver must not complete the request before the framework calls <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a>.  Otherwise, the framework might call the driver's <i>EvtRequestCancel</i> with an invalid request. For related code examples, please see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>.</p>

<p>For more information about <b>WdfRequestUnmarkCancelable</b>, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.</p>

<p>The following code example provides simplified versions of the <a href="..\wdfio\nc-wdfio-evt-wdf-io-queue-io-read.md">EvtIoRead</a>, <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> and <a href="wdf.evttimerfunc">EvtTimerFunc</a> callback functions that the <a href="wdf.sample_kmdf_drivers">ECHO sample driver</a> contains. This example shows how to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a>, <b>WdfRequestUnmarkCancelable</b>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> in a driver that uses the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>. (The ECHO sample uses device-level synchronization.)</p>

<p>If your driver does not use the framework's automatic synchronization, see the two examples on <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>. While written for a UMDF driver, these examples demonstrate techniques you can use to manage synchronization between the cancel callback and another thread that calls the <i>Unmark</i> routine.</p>

<p>A driver can call <b>WdfRequestUnmarkCancelable</b> to disable cancellation of an I/O request, if the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a> to enable cancellation of the request.</p>

<p>If <b>WdfRequestUnmarkCancelable</b> returns a value other than STATUS_CANCELLED, the driver's <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> callback function will not be called for the request.</p>

<p>If the driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>, the driver's <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> callback function can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> with a <i>Status</i> parameter of STATUS_CANCELLED. The <i>EvtRequestCancel</i> callback function does not have to call <b>WdfRequestUnmarkCancelable</b>. If the driver calls <b>WdfRequestComplete</b> outside of its <i>EvtRequestCancel</i> callback function, the driver must first call <b>WdfRequestUnmarkCancelable</b>.</p>

<p>However, the driver must not call <b>WdfRequestUnmarkCancelable</b> after <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>. In the following Example section, the example stores a local copy of the request handle and then clears it when the <i>EvtRequestCancel</i> callback function calls <b>WdfRequestComplete</b>. The driver does not call <b>WdfRequestUnmarkCancelable</b> if the local copy of the request handle has been cleared. This example uses the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>  to synchronize the callback functions.</p>

<p>Note that calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff548758">WdfObjectReference</a> to add an additional reference to the request object does <i>not</i> enable your driver to call <b>WdfRequestUnmarkCancelable</b> after the driver's <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> callback function calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>. </p>

<p>If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, and then <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> completes the request, the driver must not subsequently use the request object.</p>

<p>If <b>WdfRequestUnmarkCancelable</b> returns STATUS_CANCELLED, the driver must not complete the request before the framework calls <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a>.  Otherwise, the framework might call the driver's <i>EvtRequestCancel</i> with an invalid request. For related code examples, please see <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>.</p>

<p>For more information about <b>WdfRequestUnmarkCancelable</b>, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.</p>

<p>The following code example provides simplified versions of the <a href="..\wdfio\nc-wdfio-evt-wdf-io-queue-io-read.md">EvtIoRead</a>, <a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a> and <a href="wdf.evttimerfunc">EvtTimerFunc</a> callback functions that the <a href="wdf.sample_kmdf_drivers">ECHO sample driver</a> contains. This example shows how to call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a>, <b>WdfRequestUnmarkCancelable</b>, and <a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a> in a driver that uses the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>. (The ECHO sample uses device-level synchronization.)</p>

<p>If your driver does not use the framework's automatic synchronization, see the two examples on <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>. While written for a UMDF driver, these examples demonstrate techniques you can use to manage synchronization between the cancel callback and another thread that calls the <i>Unmark</i> routine.</p>

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
<dt>Wdfrequest.h (include Wdf.h)</dt>
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
<p>&lt;=DISPATCH_LEVEL</p>
</td>
</tr>
<tr>
<th width="30%">
<p>DDI compliance rules</p>
</th>
<td width="70%">
<a href="https://msdn.microsoft.com/library/windows/hardware/ff543501">CompleteCanceledReq</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544670">DeferredRequestCompleted</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff544957">DriverCreate</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff545711">EvtIoStopCancel</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547261">InvalidReqAccess</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff547267">InvalidReqAccessLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff548167">KmdfIrql</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/hh975091">KmdfIrql2</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff549011">MarkCancOnCancReqLocal</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551586">ReqIsCancOnCancReq</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551589">ReqMarkCancelableSend</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff551596">ReqNotCanceledLocal</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549945">WdfRequestComplete</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549983">WdfRequestMarkCancelable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549984">WdfRequestMarkCancelableEx</a>
</dt>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt-wdf-request-cancel.md">EvtRequestCancel</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestUnmarkCancelable method%20 RELEASE:%20(11/22/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
