---
UID: NF:wudfddi.IWDFIoQueue.RetrieveNextRequest
title: IWDFIoQueue::RetrieveNextRequest method
author: windows-driver-content
description: The RetrieveNextRequest method retrieves the next I/O request from an I/O queue.
old-location: wdf\iwdfioqueue_retrievenextrequest.htm
old-project: wdf
ms.assetid: 2d9dbfc8-7563-4c47-9b34-27cce2b847b2
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: IWDFIoQueue, IWDFIoQueue::RetrieveNextRequest, RetrieveNextRequest
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
req.alt-api: IWDFIoQueue.RetrieveNextRequest
req.alt-loc: WUDFx.dll
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
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---

# IWDFIoQueue::RetrieveNextRequest method



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>RetrieveNextRequest</b> method retrieves the next I/O request from an I/O queue.



## -syntax

````
HRESULT  RetrieveNextRequest(
  [out] IWDFIoRequest **ppRequest
);
````


## -parameters

### -param ppRequest [out]

A pointer to a buffer that receives a pointer to the <a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a> interface for the next request object, or receives <b>NULL</b> if the queue is empty or if the next request is not found.


## -returns
<b>RetrieveNextRequest</b> returns one of the following values:
<dl>
<dt><b>S_OK</b></dt>
</dl>The next I/O request was successfully retrieved from the I/O queue.
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_WDF_PAUSED)</b></dt>
</dl>The queue is not dispatching requests. This situation occurs if the device undergoes a power state transition and all of the queues are stopped from dispatching requests or if the driver explicitly called <a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a> to stop dispatching requests. This situation can also occur if the driver attempts to remove a request from a manual queue that is power managed and that is powered down or if the queue is paused.
<dl>
<dt><b>HRESULT_FROM_WIN32 (ERROR_NO_MORE_ITEMS)</b></dt>
</dl>No requests were in the queue.
<dl>
<dt><b>HRESULT_FROM_NT (STATUS_INVALID_DEVICE_STATE)</b></dt>
</dl>The call was made to retrieve the request from a parallel queue.

 

<b>RetrieveNextRequest</b> might also return other HRESULT values.


## -remarks
If a driver configures an I/O queue for manual dispatching of I/O requests, the driver can call the <b>RetrieveNextRequest</b> method to obtain the next request from the queue. For more information about manually dispatching I/O requests, see <a href="https://msdn.microsoft.com/7603c3fd-a4cb-4174-ad14-f57efedfe9de">Configuring Dispatch Mode for an I/O Queue</a>.

If a driver configures an I/O queue for sequential dispatching of I/O requests, the driver can still call the <b>RetrieveNextRequest</b> method to obtain the next request from the queue without receiving an error. Although the framework permits the driver to call <b>RetrieveNextRequest</b> to retrieve a request from a sequential queue, the driver should only call <b>RetrieveNextRequest</b> before the driver completes the current request. Otherwise, if the driver attempts to call <b>RetrieveNextRequest</b> after the driver completes the current request, a race condition might occur. This race condition occurs between the framework's automatic dispatching of the next request from the sequential queue and the driver's call to <b>RetrieveNextRequest</b> to retrieve the next request. 

The following code example, which is from the <a href="http://go.microsoft.com/fwlink/p/?linkid=256202">umdf_fx2</a> sample driver, polls the queue for requests for as long as requests can be retrieved. The code first verifies if requests are associated with a specific file object.


## -see-also
<dl>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a>
</dt>
<dt>
<a href="..\wudfddi\nn-wudfddi-iwdfiorequest.md">IWDFIoRequest</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoQueue::RetrieveNextRequest method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

