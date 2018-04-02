---
UID: NF:wudfddi.IWDFIoRequest.CancelSentRequest
title: IWDFIoRequest::CancelSentRequest method
author: windows-driver-content
description: The CancelSentRequest method attempts to cancel the I/O request that the driver previously submitted to an I/O target.
old-location: wdf\iwdfiorequest_cancelsentrequest.htm
old-project: wdf
ms.assetid: 1951a2e8-c2f0-42bc-9deb-8d2a049817c4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: CancelSentRequest method, CancelSentRequest method, IWDFIoRequest interface, CancelSentRequest,IWDFIoRequest.CancelSentRequest, IWDFIoRequest, IWDFIoRequest interface, CancelSentRequest method, IWDFIoRequest::CancelSentRequest, UMDFRequestObjectRef_cf439791-044b-4cd8-8a1c-eafc7b266897.xml, umdf.iwdfiorequest_cancelsentrequest, wdf.iwdfiorequest_cancelsentrequest, wudfddi/IWDFIoRequest::CancelSentRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.5
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: WUDFx.dll
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	WUDFx.dll
api_name:
-	IWDFIoRequest.CancelSentRequest
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoRequest::CancelSentRequest method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>CancelSentRequest</b> method attempts to cancel the I/O request that the driver previously submitted to an I/O target.

## Syntax

```
BOOL CancelSentRequest(

);
```

## Parameters

This function has no parameters.

## Return Value

<b>CancelSentRequest</b> returns a BOOL value that indicates whether the cancel request was successfully delivered to the request's owner. <b>TRUE</b> indicates the request was successfully delivered. <b>FALSE</b> indicates the request was not successfully delivered.

## Remarks

A driver can call <b>CancelSentRequest</b> to attempt to cancel the I/O request that it previously sent to an I/O target by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a> method.

If the request is in the I/O target's queue, the framework cancels the request. If the framework already delivered the request to the I/O target's driver, and if that driver previously called <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> to enabling canceling, the framework calls that driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a> method. If the target's driver did not call <b>IWDFIoRequest::MarkCancelable</b>, the request is not canceled unless the request subsequently becomes cancelable.

If the driver previously registered the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556904">IRequestCallbackRequestCompletion</a> interface for the request's completion routine, the framework calls the completion routine after the request is canceled.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556903">IRequestCallbackCancel::OnCancel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556904">IRequestCallbackRequestCompletion</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558985">IWDFIoRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559149">IWDFIoRequest::Send</a>