---
UID: NE.wdfio._WDF_IO_QUEUE_DISPATCH_TYPE
title: _WDF_IO_QUEUE_DISPATCH_TYPE
author: windows-driver-content
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration type identifies the request dispatching methods that can be associated with a framework queue object.
old-location: wdf\wdf_io_queue_dispatch_type.htm
old-project: wdf
ms.assetid: 90f2f490-ee29-4e20-94b2-65a9bba3e831
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: _WDF_IO_QUEUE_DISPATCH_TYPE, WDF_IO_QUEUE_DISPATCH_TYPE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.alt-api: WDF_IO_QUEUE_DISPATCH_TYPE
req.alt-loc: wdfio.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL (see Remarks section)
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_DISPATCH_TYPE enumeration



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]
The <b>WDF_IO_QUEUE_DISPATCH_TYPE</b> enumeration type identifies the request dispatching methods that can be associated with a framework queue object. 


## -syntax

````
typedef enum _WDF_IO_QUEUE_DISPATCH_TYPE { 
  WdfIoQueueDispatchInvalid     = 0,
  WdfIoQueueDispatchSequential  = 1,
  WdfIoQueueDispatchParallel    = 2,
  WdfIoQueueDispatchManual      = 3,
  WdfIoQueueDispatchMax         = 4
} WDF_IO_QUEUE_DISPATCH_TYPE;
````


## -enum-fields

### -field WdfIoQueueDispatchInvalid

Reserved for internal use.

### -field WdfIoQueueDispatchSequential

The I/O queue's requests are presented to the driver's <a href="wdf.request_handlers">request handlers</a> one at a time. The framework does not deliver the next request until a driver has called <a href="wdf.wdfrequestcomplete">WdfRequestComplete</a> to complete the current request.

### -field WdfIoQueueDispatchParallel

The framework presents requests to the driver's request handlers as soon as the requests are available. 

### -field WdfIoQueueDispatchManual

The framework places requests into the queue but does not deliver them to the driver. The driver must retrieve requests from the queue by calling <a href="wdf.wdfioqueueretrievenextrequest">WdfIoQueueRetrieveNextRequest</a>.

### -field WdfIoQueueDispatchMax

Reserved for internal use only.

## -remarks
For more information, see <a href="wdf.dispatching_methods_for_i_o_requests">Dispatching Methods for I/O Requests</a>.

## -requirements
<table>
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
<dt>Wdfio.h (include Wdf.h)</dt>
</dl>
</td>
</tr>
</table>