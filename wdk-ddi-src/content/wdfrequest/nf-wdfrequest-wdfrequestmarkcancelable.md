---
UID: NF.wdfrequest.WdfRequestMarkCancelable
title: WdfRequestMarkCancelable function
author: windows-driver-content
description: The WdfRequestMarkCancelable method enables cancellation of a specified I/O request.
old-location: wdf\wdfrequestmarkcancelable.htm
old-project: wdf
ms.assetid: 1bd1ec2a-8b07-4843-84b6-6b651453328c
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfRequestMarkCancelable
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
req.alt-api: WdfRequestMarkCancelable
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DeferredRequestCompleted, DriverCreate, EvtIoStopCancel, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2, MarkCancOnCancReqLocal, ReqIsCancOnCancReq, ReqMarkCancelableSend, ReqNotCanceledLocal, RequestCompleted, RequestCompletedLocal
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: <=DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# WdfRequestMarkCancelable function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestMarkCancelable</b> method enables cancellation of a specified I/O request.



## -syntax

````
VOID WdfRequestMarkCancelable(
  _In_ WDFREQUEST             Request,
  _In_ PFN_WDF_REQUEST_CANCEL EvtRequestCancel
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


### -param EvtRequestCancel [in]

A pointer to a driver-defined <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function, which the framework calls if it cancels the I/O request.


## -returns
None.

A bug check occurs if the driver supplies an invalid object handle.


## -remarks
After your driver has <a href="wdf.receiving_i_o_requests">received an I/O request</a> from the framework, the driver can call <b>WdfRequestMarkCancelable</b> or, starting with  KMDF version 1.9, <a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> to make the request cancelable.

When calling <b>WdfRequestMarkCancelable</b>, your driver must specify an <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function. The framework calls the callback function if the I/O manager or another driver is attempting to cancel the I/O request.

If your driver uses the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>, the driver can call either <b>WdfRequestMarkCancelable</b> or <a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>.

If the driver does not use automatic synchronization, it must call <a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> instead of <b>WdfRequestMarkCancelable</b> for the following reasons:

If the specified request has already been canceled, <b>WdfRequestMarkCancelable</b> calls the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function before returning. If the driver acquires a spinlock before calling <b>WdfRequestMarkCancelable</b> and attempts to acquire the same spinlock inside  <i>EvtRequestCancel</i>, the same thread attempts to acquire the same spinlock twice, causing a deadlock.

However, because <a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> never calls <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>, this scenario does not occur. If the request has already been canceled, <b>WdfRequestMarkCancelableEx</b> returns <b>STATUS_CANCELLED</b>. If your driver acquires a spinlock (which sets the IRQL to DISPATCH_LEVEL) before calling <b>WdfRequestMarkCancelableEx</b> and releases the spinlock (which sets the IRQL to PASSIVE_LEVEL) after <b>WdfRequestMarkCancelableEx</b> returns, the <i>EvtRequestCancel</i> callback function will not be called before the spinlock is released. Therefore, a deadlock does not occur even if the <i>EvtRequestCancel</i> callback function uses the same spinlock.

After a driver calls <b>WdfRequestMarkCancelable</b> to enable canceling, the request remains cancelable while the driver <a href="wdf.request_ownership">owns</a> the request object, unless the driver calls <a href="wdf.wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>. 

If a driver has called <b>WdfRequestMarkCancelable</b>, and if the driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function has not executed and called <a href="wdf.wdfrequestcomplete">WdfRequestComplete</a>, the driver must call <a href="wdf.wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> before it calls <b>WdfRequestComplete</b> outside of the <i>EvtRequestCancel</i> callback function.

If the driver calls <a href="wdf.wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a> to forward the request to a different queue, the following rules apply:

I/O requests cannot be cancelable when your driver forwards them to a different queue. 

Generally, your driver should not call <b>WdfRequestMarkCancelable</b> to enable canceling the request before calling <a href="wdf.wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>. If the driver does make the request cancelable, it must call <a href="wdf.wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a> to disable cancellation before calling <b>WdfRequestForwardToIoQueue</b>.

While the request is in the second queue, the framework owns it and can cancel it without notifying the driver.

If the driver requires cancellation notification (so that it can deallocate any resources that it might have allocated before calling <a href="wdf.wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>), the driver should register an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_canceled_on_queue.md">EvtIoCanceledOnQueue</a> callback function, and it should use request-specific context memory to store information about the request's resources.

After the framework has dequeued the request from the second queue and delivered it to the driver, the driver can call <b>WdfRequestMarkCancelable</b> to enable canceling.

For more information about <b>WdfRequestMarkCancelable</b>, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.

The following code example shows parts of two callback functions: 

An <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_read.md">EvtIoRead</a> callback function that performs request-specific work (such as creating subrequests to send to an I/O target), then enables cancellation of the received I/O request.

An <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function that cancels an I/O request.

The driver must use the framework's <a href="wdf.using_automatic_synchronization">automatic synchronization</a>.


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
<dt>Wdfrequest.h (include Wdf.h)</dt>
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
&lt;=DISPATCH_LEVEL

</td>
</tr>
<tr>
<th width="30%">
DDI compliance rules

</th>
<td width="70%">
<a href="devtest.kmdf_deferredrequestcompleted">DeferredRequestCompleted</a>, <a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_evtiostopcancel">EvtIoStopCancel</a>, <a href="devtest.kmdf_invalidreqaccess">InvalidReqAccess</a>, <a href="devtest.kmdf_invalidreqaccesslocal">InvalidReqAccessLocal</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>, <a href="devtest.kmdf_markcanconcancreqlocal">MarkCancOnCancReqLocal</a>, <a href="devtest.kmdf_reqiscanconcancreq">ReqIsCancOnCancReq</a>, <a href="devtest.kmdf_reqmarkcancelablesend">ReqMarkCancelableSend</a>, <a href="devtest.kmdf_reqnotcanceledlocal">ReqNotCanceledLocal</a>, <a href="devtest.kmdf_requestcompleted">RequestCompleted</a>, <a href="devtest.kmdf_requestcompletedlocal">RequestCompletedLocal</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfrequestcomplete">WdfRequestComplete</a>
</dt>
<dt>
<a href="wdf.wdfrequestforwardtoioqueue">WdfRequestForwardToIoQueue</a>
</dt>
<dt>
<a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>
</dt>
<dt>
<a href="wdf.wdfrequestunmarkcancelable">WdfRequestUnmarkCancelable</a>
</dt>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestMarkCancelable method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

