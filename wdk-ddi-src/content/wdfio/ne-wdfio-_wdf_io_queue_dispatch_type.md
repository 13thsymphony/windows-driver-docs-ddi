---
UID: NE:wdfio._WDF_IO_QUEUE_DISPATCH_TYPE
title: "_WDF_IO_QUEUE_DISPATCH_TYPE"
author: windows-driver-content
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration type identifies the request dispatching methods that can be associated with a framework queue object.
old-location: wdf\wdf_io_queue_dispatch_type.htm
old-project: wdf
ms.assetid: 90f2f490-ee29-4e20-94b2-65a9bba3e831
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdfio/WdfIoQueueDispatchParallel, wdfio/WdfIoQueueDispatchMax, kmdf.wdf_io_queue_dispatch_type, WdfIoQueueDispatchParallel, wdfio/WdfIoQueueDispatchManual, WDF_IO_QUEUE_DISPATCH_TYPE enumeration, wdfio/WdfIoQueueDispatchInvalid, wdfio/WdfIoQueueDispatchSequential, WDF_IO_QUEUE_DISPATCH_TYPE, WdfIoQueueDispatchManual, wdf.wdf_io_queue_dispatch_type, WdfIoQueueDispatchInvalid, WdfIoQueueDispatchMax, DFQueueObjectRef_dd3d1037-0355-4f02-b0ec-4bd988df33d2.xml, _WDF_IO_QUEUE_DISPATCH_TYPE, wdfio/WDF_IO_QUEUE_DISPATCH_TYPE, WdfIoQueueDispatchSequential
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL (see Remarks section)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	wdfio.h
apiname:
-	WDF_IO_QUEUE_DISPATCH_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_DISPATCH_TYPE Enumeration
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_DISPATCH_TYPE</b> enumeration type identifies the request dispatching methods that can be associated with a framework queue object.

## Syntax
````
typedef enum _WDF_IO_QUEUE_DISPATCH_TYPE { 
  WdfIoQueueDispatchInvalid     = 0,
  WdfIoQueueDispatchSequential  = 1,
  WdfIoQueueDispatchParallel    = 2,
  WdfIoQueueDispatchManual      = 3,
  WdfIoQueueDispatchMax         = 4
} WDF_IO_QUEUE_DISPATCH_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WdfIoQueueDispatchInvalid</td>
                    <td>Reserved for internal use.</td>
                </tr>
            
                <tr>
                    <td>WdfIoQueueDispatchManual</td>
                    <td>The framework places requests into the queue but does not deliver them to the driver. The driver must retrieve requests from the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueueretrievenextrequest.md">WdfIoQueueRetrieveNextRequest</a>.</td>
                </tr>
            
                <tr>
                    <td>WdfIoQueueDispatchMax</td>
                    <td>Reserved for internal use only.</td>
                </tr>
            
                <tr>
                    <td>WdfIoQueueDispatchParallel</td>
                    <td>The framework presents requests to the driver's request handlers as soon as the requests are available.</td>
                </tr>
            
                <tr>
                    <td>WdfIoQueueDispatchSequential</td>
                    <td>The I/O queue's requests are presented to the driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handlers</a> one at a time. The framework does not deliver the next request until a driver has called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> to complete the current request.</td>
                </tr>
</table>

    ## Remarks

        For more information, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/dispatching-methods-for-i-o-requests">Dispatching Methods for I/O Requests</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfio.h (include Wdf.h) |