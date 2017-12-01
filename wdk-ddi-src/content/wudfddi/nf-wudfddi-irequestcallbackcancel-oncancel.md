---
UID: NF.wudfddi.IRequestCallbackCancel.OnCancel
title: IRequestCallbackCancel::OnCancel
author: windows-driver-content
description: The OnCancel method is called when an application cancels an I/O operation through the Microsoft Win32 CancelIo, CancelIoEx, or CancelSynchronousIo function.
old-location: wdf\irequestcallbackcancel_oncancel.htm
old-project: wdf
ms.assetid: 67c85eaa-bb47-4384-8e37-fdbbc879b352
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: IRequestCallbackCancel, OnCancel, IRequestCallbackCancel::OnCancel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IRequestCallbackCancel.OnCancel
req.alt-loc: Wudfddi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: IRequestCallbackCancel
req.product: Windows 10 or later.
---

# IRequestCallbackCancel::OnCancel method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]</p>
<p>The <b>OnCancel</b> method is called when an application cancels an I/O operation through the Microsoft Win32 <b>CancelIo</b>, <b>CancelIoEx</b>, or <b>CancelSynchronousIo</b> function. </p>


## -syntax

````
void OnCancel(
  [in] IWDFIoRequest *pWdfRequest
);
````


## -parameters
<dl>

### -param <i>pWdfRequest</i> [in]

<dd>
<p>A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface that represents the framework request object to cancel. </p>
</dd>
</dl>

## -returns
<p>None</p>

## -remarks
<p>The framework calls the <b>OnCancel</b> method to cancel the I/O request that the <i>pWdfRequest</i> parameter identifies. The driver should first determine whether it can cancel the I/O request. If the request can be canceled, the driver should cancel it. For more information about how to cancel a request, see <a href="wdf.canceling_i_o_requests">Canceling I/O Requests</a>.</p>

<p>If the driver cancels the request, the driver must also complete the request by calling the <a href="wdf.iwdfiorequest_complete">IWDFIoRequest::Complete</a> method with the <i>CompletionStatus</i> parameter set to HRESULT_FROM_WIN32(ERROR_OPERATION_ABORTED). </p>

<p>The framework does not call <b>OnCancel</b> to cancel a request unless the driver previously called the <a href="wdf.iwdfiorequest_markcancelable">IWDFIoRequest::MarkCancelable</a> method to enable cancellation of the request and to register the <a href="..\wudfddi\nn-wudfddi-irequestcallbackcancel.md">IRequestCallbackCancel</a> interface.</p>

<p>The User-Mode Driver Framework (UMDF) allows only one <b>OnCancel</b> method per queue. Therefore, when a driver calls <a href="wdf.iwdfiorequest_markcancelable">IWDFIoRequest::MarkCancelable</a> for requests that are associated with a particular queue to enable the framework to cancel those requests, the driver must pass a pointer to the <a href="..\wudfddi\nn-wudfddi-irequestcallbackcancel.md">IRequestCallbackCancel</a> interface for the same request-callback object. Later, to cancel each request, the framework passes a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the request in a call to this request-callback object's <b>OnCancel</b> method.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wudfddi.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-irequestcallbackcancel.md">IRequestCallbackCancel</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_complete">IWDFIoRequest::Complete</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_markcancelable">IWDFIoRequest::MarkCancelable</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IRequestCallbackCancel::OnCancel method%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
