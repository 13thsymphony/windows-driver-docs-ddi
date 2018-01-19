---
UID : NF:wudfddi.IWDFIoRequest.ForwardToIoQueue
title : IWDFIoRequest::ForwardToIoQueue method
author : windows-driver-content
description : The ForwardToIoQueue method forwards (that is, requeues) an I/O request to one of the calling driver's I/O queues.
old-location : wdf\iwdfiorequest_forwardtoioqueue.htm
old-project : wdf
ms.assetid : 07317157-1222-4b34-89f4-d546818e9851
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : IWDFIoRequest, IWDFIoRequest::ForwardToIoQueue, ForwardToIoQueue
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : method
req.header : wudfddi.h
req.include-header : Wudfddi.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 1.5
req.alt-api : IWDFIoRequest.ForwardToIoQueue
req.alt-loc : WUDFx.dll
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : Unavailable in UMDF 2.0 and later.
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : WUDFx.dll
req.irql : 
req.typenames : "*PPOWER_ACTION, POWER_ACTION"
req.product : Windows 10 or later.
---


# ForwardToIoQueue method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>ForwardToIoQueue</b> method forwards (that is, requeues) an I/O request to one of the calling driver's I/O queues.

## Syntax

````
HRESULT ForwardToIoQueue(
  [in] IWDFIoQueue *pDestination
);
````

## Parameters

`pDestination`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the destination queue object.


## Return Value

<b>ForwardToIoQueue</b> returns S_OK if the operation succeeds. Otherwise, this method returns one of the error codes that are defined in Winerror.h.

## Remarks

The driver must own the I/O request and must have obtained the request from one of its I/O queues.

The source and destination queues cannot be the same. In other words, the driver cannot call <b>ForwardToIoQueue</b> to return a request to the queue that it came from. To return an I/O request to the I/O queue that it came from, the driver can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff559028">IWDFIoRequest2::Requeue</a>.

Both the source and destination queues must belong to the same device.

Also, the <b>ForwardToIoQueue</b> method cannot requeue a request that the driver obtained by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a> method.

The request cannot be cancelable. If the driver previously called the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a> method to make the request cancelable, the driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a> method before calling <b>ForwardToIoQueue</b>.

The following code example shows how to forward a request to another queue if the request's buffer is insufficient to hold the required information.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559146">IWDFIoRequest::MarkCancelable</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff559163">IWDFIoRequest::UnmarkCancelable</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoRequest::ForwardToIoQueue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>