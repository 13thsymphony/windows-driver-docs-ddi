---
UID: NF.wdfrequest.WdfRequestCancelSentRequest
title: WdfRequestCancelSentRequest function
author: windows-driver-content
description: The WdfRequestCancelSentRequest method attempts to cancel an I/O request that the caller previously submitted to an I/O target.
old-location: wdf\wdfrequestcancelsentrequest.htm
old-project: wdf
ms.assetid: 24319054-5e5c-4330-86e5-b1527c48eaf2
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: WdfRequestCancelSentRequest
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
req.alt-api: WdfRequestCancelSentRequest
req.alt-loc: Wdf01000.sys,Wdf01000.sys.dll,WUDFx02000.dll,WUDFx02000.dll.dll
req.ddi-compliance: DriverCreate, EvtIoStopCancel, EvtIoStopCompleteOrStopAck, InvalidReqAccess, InvalidReqAccessLocal, KmdfIrql, KmdfIrql2
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

# WdfRequestCancelSentRequest function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfRequestCancelSentRequest</b> method attempts to cancel an I/O request that the caller previously submitted to an I/O target.



## -syntax

````
BOOLEAN WdfRequestCancelSentRequest(
  _In_ WDFREQUEST Request
);
````


## -parameters

### -param Request [in]

A handle to a framework request object.


## -returns
<b>WdfRequestCancelSentRequest</b> returns <b>TRUE</b> if it successfully delivers the cancel request to the driver's I/O target. This method returns <b>FALSE</b> if the request has already been completed or canceled, or if the I/O target driver has not called <a href="wdf.wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>.

A bug check occurs if the driver supplies an invalid object handle.




## -remarks
A driver can call <b>WdfRequestCancelSentRequest</b> to attempt to cancel an I/O request that it previously had sent to an I/O target by calling <a href="wdf.wdfrequestsend">WdfRequestSend</a>.

If the request is in the I/O target's queue, the framework cancels the request. If the framework has already delivered the request to the I/O target's driver, and if that driver has called <a href="wdf.wdfrequestmarkcancelable">WdfRequestMarkCancelable</a> or <a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a> to enable canceling, the framework calls that driver's <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a> callback function. If the target's driver has not called <b>WdfRequestMarkCancelable</b> or <b>WdfRequestMarkCancelableEx</b>, the request is not canceled unless the request becomes cancelable.

If the driver has registered a <a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a> callback function for the request, the framework calls the callback function after the request has been canceled.

Typically, if your driver calls <b>WdfRequestCancelSentRequest</b>, it must increment the request object's reference count. For more information, see <a href="wdf.synchronizing_cancellation_of_sent_requests">Synchronizing Cancellation of Sent Requests</a>.

For more information about request cancellation, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.

The following code example is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256131">kmdf_fx2</a> sample driver. This example is an <a href="..\wdfio\nc-wdfio-evt_wdf_io_queue_io_stop.md">EvtIoStop</a> callback function. Because this driver sends each request to its I/O target, the <i>EvtIoStop</i> callback function calls <b>WdfRequestCancelSentRequest</b> if the device has been removed.


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
<a href="devtest.kmdf_drivercreate">DriverCreate</a>, <a href="devtest.kmdf_evtiostopcancel">EvtIoStopCancel</a>, <a href="devtest.kmdf_evtiostopcompleteorstopack">EvtIoStopCompleteOrStopAck</a>, <a href="devtest.kmdf_invalidreqaccess">InvalidReqAccess</a>, <a href="devtest.kmdf_invalidreqaccesslocal">InvalidReqAccessLocal</a>, <a href="devtest.kmdf_kmdfirql">KmdfIrql</a>, <a href="devtest.kmdf_kmdfirql2">KmdfIrql2</a>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.wdfrequestmarkcancelable">WdfRequestMarkCancelable</a>
</dt>
<dt>
<a href="wdf.wdfrequestmarkcancelableex">WdfRequestMarkCancelableEx</a>
</dt>
<dt>
<a href="wdf.wdfrequestsend">WdfRequestSend</a>
</dt>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_completion_routine.md">CompletionRoutine</a>
</dt>
<dt>
<a href="..\wdfrequest\nc-wdfrequest-evt_wdf_request_cancel.md">EvtRequestCancel</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfRequestCancelSentRequest method%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

