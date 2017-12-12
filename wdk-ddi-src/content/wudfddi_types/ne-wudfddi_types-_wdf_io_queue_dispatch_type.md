---
UID: NE.wudfddi_types._WDF_IO_QUEUE_DISPATCH_TYPE
title: _WDF_IO_QUEUE_DISPATCH_TYPE
author: windows-driver-content
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration contains values that identify how a driver must receive requests from an I/O queue.
old-location: wdf\wdf_io_queue_dispatch_type_umdf.htm
old-project: wdf
ms.assetid: 40f4cd91-ba84-426c-b248-6027d1e8d1a4
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDF_IO_QUEUE_DISPATCH_TYPE, WDF_IO_QUEUE_DISPATCH_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wudfddi_types.h
req.include-header: Wudfddi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDF_IO_QUEUE_DISPATCH_TYPE
req.alt-loc: Wudfddi_types.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_DISPATCH_TYPE enumeration



## -description
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


      The <a href="wdf.wdf_io_queue_dispatch_type">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumeration contains values that identify how a driver must receive requests from an I/O queue.



## -syntax

````
typedef enum _WDF_IO_QUEUE_DISPATCH_TYPE { 
  WdfIoQueueDispatchSequential  = 1,
  WdfIoQueueDispatchParallel    = 2,
  WdfIoQueueDispatchManual      = 3,
  WdfIoQueueDispatchMaximum     = ( WdfIoQueueDispatchManual + 1 )
} WDF_IO_QUEUE_DISPATCH_TYPE;
````


## -enum-fields

### -field WdfIoQueueDispatchSequential

The I/O queue's requests are presented to the driver's I/O queue callback functions one at a time. The framework delivers the next request after the driver calls the <a href="wdf.iwdfiorequest_complete">IWDFIoRequest::Complete</a> method to complete the current request.


### -field WdfIoQueueDispatchParallel

The framework presents requests to the driver's I/O queue callback functions as soon as the requests are available.


### -field WdfIoQueueDispatchManual

The framework places requests into the queue but does not deliver them to the driver. The driver must call the <a href="wdf.iwdfioqueue_retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a> method to retrieve a request from the queue.


### -field WdfIoQueueDispatchMaximum

Valid enumeration values were exceeded.


## -remarks


## -requirements
<table>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Wudfddi_types.h (include Wudfddi.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="wdf.iwdfioqueue_retrievenextrequest">IWDFIoQueue::RetrieveNextRequest</a>
</dt>
<dt>
<a href="wdf.iwdfiorequest_complete">IWDFIoRequest::Complete</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_DISPATCH_TYPE enumeration%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

