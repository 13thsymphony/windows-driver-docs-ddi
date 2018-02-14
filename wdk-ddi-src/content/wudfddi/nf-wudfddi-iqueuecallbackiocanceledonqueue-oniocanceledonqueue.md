---
UID: NF:wudfddi.IQueueCallbackIoCanceledOnQueue.OnIoCanceledOnQueue
title: IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue method
author: windows-driver-content
description: A driver's OnIoCanceledOnQueue event callback function informs the driver that an I/O request was canceled while it was in an I/O queue.
old-location: wdf\iqueuecallbackiocanceledonqueue_oniocanceledonqueue.htm
old-project: wdf
ms.assetid: 901ff312-d1bb-46bf-b8e6-6abc47fa3c7f
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: OnIoCanceledOnQueue method, IQueueCallbackIoCanceledOnQueue interface, OnIoCanceledOnQueue method, IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue, IQueueCallbackIoCanceledOnQueue, UMDFQueueObjectRef_e80a1257-b51e-46f8-8e9f-0fff3b830587.xml, OnIoCanceledOnQueue, umdf.iqueuecallbackiocanceledonqueue_oniocanceledonqueue, wdf.iqueuecallbackiocanceledonqueue_oniocanceledonqueue, IQueueCallbackIoCanceledOnQueue interface, OnIoCanceledOnQueue method, wudfddi/IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
req.include-header: Wudfddi.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 1.9
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: Unavailable in UMDF 2.0 and later.
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: wudfddi.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	COM
apilocation:
-	Wudfddi.h
apiname:
-	IQueueCallbackIoCanceledOnQueue.OnIoCanceledOnQueue
product: Windows
targetos: Windows
req.typenames: "*PPOWER_ACTION, POWER_ACTION"
req.product: Windows 10 or later.
---


# OnIoCanceledOnQueue method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

A driver's <b>OnIoCanceledOnQueue</b> event callback function informs the driver that an I/O request was canceled while it was in an I/O queue.

## Syntax

````
void OnIoCanceledOnQueue(
  [in] IWDFIoQueue   *pWdfQueue,
  [in] IWDFIoRequest *pWdfRequest
);
````

## Parameters

`pWdfQueue`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a> interface for the I/O queue that the I/O request was in when it was canceled.

`pWdfRequest`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the I/O request.


## Return Value

None.

## Remarks

A driver registers an I/O queue's <a href="..\wudfddi\nn-wudfddi-iqueuecallbackiocanceledonqueue.md">IQueueCallbackIoCanceledOnQueue</a> interface and <b>OnIoCanceledOnQueue</b> callback function when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>. For more information about how to register the interface, see <a href="..\wudfddi\nn-wudfddi-iqueuecallbackiocanceledonqueue.md">IQueueCallbackIoCanceledOnQueue</a>.

If a driver registers an <b>OnIoCanceledOnQueue</b> callback function for an I/O queue, the framework calls the callback function if a request handler receives an I/O request from an I/O queue, the driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff559081">IWDFIoRequest::ForwardToIoQueue</a> or <a href="https://msdn.microsoft.com/library/windows/hardware/ff559028">IWDFIoRequest2::Requeue</a> to requeue the request to the I/O queue for which the <b>OnIoCanceledOnQueue</b> callback function is registered, and the associated I/O operation is subsequently canceled.

After the framework calls the <b>OnIoCanceledOnQueue</b> callback function, the driver owns the request object and, therefore, must <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">cancel</a> the request.

The framework does not call the driver's <b>OnIoCanceledOnQueue</b> callback function for I/O requests that the framework has never delivered to the driver.

The framework calls an <b>OnIoCanceledOnQueue</b> callback function as soon as it determines that an I/O request has been canceled, regardless of the <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/configuring-dispatch-mode-for-an-i-o-queue">dispatching method</a> that the driver has set for the I/O queue. Therefore, the framework can call an <b>OnIoCanceledOnQueue</b> callback function for a request in a queue that uses sequential dispatching, even if the driver currently owns another request from the queue.

For more information about the <b>OnIoCanceledOnQueue</b> callback function, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/canceling-i-o-requests">Canceling I/O Requests</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.9 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **Library** | wudfddi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff559081">IWDFIoRequest::ForwardToIoQueue</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackiocanceledonqueue.md">IQueueCallbackIoCanceledOnQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IQueueCallbackIoCanceledOnQueue::OnIoCanceledOnQueue method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>