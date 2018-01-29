---
UID : NF:wdfio.WdfIoQueueStart
title : WdfIoQueueStart function
author : windows-driver-content
description : The WdfIoQueueStart method enables an I/O queue to start receiving and delivering new I/O requests.
old-location : wdf\wdfioqueuestart.htm
old-project : wdf
ms.assetid : 1ce8a447-6205-44d0-b5d2-b78f01e15bb4
ms.author : windowsdriverdev
ms.date : 1/11/2018
ms.keywords : wdfio/WdfIoQueueStart, kmdf.wdfioqueuestart, WdfIoQueueStart method, WdfIoQueueStart, DFQueueObjectRef_15829d65-ee6a-455d-a0c6-cf21f5426e31.xml, PFN_WDFIOQUEUESTART, wdf.wdfioqueuestart
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : wdfio.h
req.include-header : Wdf.h
req.target-type : Universal
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.ddi-compliance : DriverCreate, KmdfIrql, KmdfIrql2
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDF_IO_QUEUE_STATE
req.product : Windows 10 or later.
---


# WdfIoQueueStart function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfIoQueueStart</b> method enables an I/O queue to start receiving and delivering new I/O requests.

## Syntax

````
VOID WdfIoQueueStart(
  _In_ WDFQUEUE Queue
);
````

## Parameters

`Queue`

A handle to a framework queue object.


## Return Value

None.

A bug check occurs if the driver supplies an invalid object handle.

## Remarks

If I/O requests are in the I/O queue when the driver calls <b>WdfIoQueueStart</b>, the same thread that calls <b>WdfIoQueueStart</b> can call the driver's <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handlers</a> before <b>WdfIoQueueStart</b> returns. Therefore, when the driver calls <b>WdfIoQueueStart</b>, it must not hold any <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/using-framework-locks">locks</a> that the request handlers attempt to acquire. Otherwise, a deadlock can result.

For more information about the <b>WdfIoQueueStart</b> method, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/managing-i-o-queues">Managing I/O Queues</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfio.h (include Wdf.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | DriverCreate, KmdfIrql, KmdfIrql2 |

## See Also

<a href="..\wdfio\nf-wdfio-wdfioqueuestop.md">WdfIoQueueStop</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfIoQueueStart method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>