---
UID: NE:wdfio._WDF_IO_QUEUE_DISPATCH_TYPE
title: _WDF_IO_QUEUE_DISPATCH_TYPE
author: windows-driver-content
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration type identifies the request dispatching methods that can be associated with a framework queue object.
old-location: wdf\wdf_io_queue_dispatch_type.htm
old-project: wdf
ms.assetid: 90f2f490-ee29-4e20-94b2-65a9bba3e831
ms.author: windowsdriverdev
ms.date: 1/11/2018
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
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
req.typenames: WDF_IO_QUEUE_DISPATCH_TYPE
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

The I/O queue's requests are presented to the driver's <a href="https://msdn.microsoft.com/bfc543bf-18a8-4e2c-ba7a-d0a21cefb038">request handlers</a> one at a time. The framework does not deliver the next request until a driver has called <a href="..\wdfrequest\nf-wdfrequest-wdfrequestcomplete.md">WdfRequestComplete</a> to complete the current request.


### -field WdfIoQueueDispatchParallel

The framework presents requests to the driver's request handlers as soon as the requests are available. 


### -field WdfIoQueueDispatchManual

The framework places requests into the queue but does not deliver them to the driver. The driver must retrieve requests from the queue by calling <a href="..\wdfio\nf-wdfio-wdfioqueueretrievenextrequest.md">WdfIoQueueRetrieveNextRequest</a>.


### -field WdfIoQueueDispatchMax

Reserved for internal use only.


## -remarks
For more information, see <a href="https://msdn.microsoft.com/3e91aa7c-bccf-4eeb-8b68-b1277a690f8c">Dispatching Methods for I/O Requests</a>.</p>