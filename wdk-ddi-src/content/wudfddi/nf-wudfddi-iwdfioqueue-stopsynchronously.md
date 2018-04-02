---
UID: NF:wudfddi.IWDFIoQueue.StopSynchronously
title: IWDFIoQueue::StopSynchronously method
author: windows-driver-content
description: The StopSynchronously method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.
old-location: wdf\iwdfioqueue_stopsynchronously.htm
old-project: wdf
ms.assetid: ea05cb82-8a50-48d8-a15c-b7ab58c01b30
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IWDFIoQueue, IWDFIoQueue interface, StopSynchronously method, IWDFIoQueue::StopSynchronously, StopSynchronously method, StopSynchronously method, IWDFIoQueue interface, StopSynchronously,IWDFIoQueue.StopSynchronously, UMDFQueueObjectRef_18e42c5a-ade3-4d81-8af1-bd19655650e7.xml, umdf.iwdfioqueue_stopsynchronously, wdf.iwdfioqueue_stopsynchronously, wudfddi/IWDFIoQueue::StopSynchronously
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
-	IWDFIoQueue.StopSynchronously
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IWDFIoQueue::StopSynchronously method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>StopSynchronously</b> method prevents an I/O queue from delivering I/O requests, but the queue receives and stores new requests. The method returns after all delivered requests have been canceled or completed.

## Syntax

```
void StopSynchronously(

);
```

## Parameters

This function has no parameters.

## Return Value

None

## Remarks

The <b>StopSynchronously</b> method is the synchronous version of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a> method. That is, <b>StopSynchronously</b> does not return to the driver until the queue stops.

The <b>StopSynchronously</b> method enables the queue to receive new requests, even if the queue was not receiving new requests before the driver called <b>StopSynchronously</b>. For example, a driver might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff558951">IWDFIoQueue::Drain</a>, which causes the framework to stop adding new I/O requests to the queue. The driver's subsequent call of <b>StopSynchronously</b> causes the framework to resume adding requests to the queue.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a>