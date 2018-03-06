---
UID: NE:wudfddi_types._WDF_IO_QUEUE_DISPATCH_TYPE
title: "_WDF_IO_QUEUE_DISPATCH_TYPE"
author: windows-driver-content
description: The WDF_IO_QUEUE_DISPATCH_TYPE enumeration contains values that identify how a driver must receive requests from an I/O queue.
old-location: wdf\wdf_io_queue_dispatch_type_umdf.htm
old-project: wdf
ms.assetid: 40f4cd91-ba84-426c-b248-6027d1e8d1a4
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: WDF_IO_QUEUE_DISPATCH_TYPE, WDF_IO_QUEUE_DISPATCH_TYPE enumeration, WdfIoQueueDispatchManual, WdfIoQueueDispatchMaximum, WdfIoQueueDispatchParallel, WdfIoQueueDispatchSequential, _WDF_IO_QUEUE_DISPATCH_TYPE, umdf.wdf_io_queue_dispatch_type, umdfstructs_7f7744f6-7f47-4e8e-a74d-fb0217a59f34.xml, wdf.wdf_io_queue_dispatch_type_umdf, wudfddi_types/WDF_IO_QUEUE_DISPATCH_TYPE, wudfddi_types/WdfIoQueueDispatchManual, wudfddi_types/WdfIoQueueDispatchMaximum, wudfddi_types/WdfIoQueueDispatchParallel, wudfddi_types/WdfIoQueueDispatchSequential
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wudfddi_types.h
api_name:
-	WDF_IO_QUEUE_DISPATCH_TYPE
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_DISPATCH_TYPE
req.product: Windows 10 or later.
---

# _WDF_IO_QUEUE_DISPATCH_TYPE Enumeration
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]


The <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_dispatch_type.md">WDF_IO_QUEUE_DISPATCH_TYPE</a> enumeration contains values that identify how a driver must receive requests from an I/O queue.

## Syntax
````
typedef enum _WDF_IO_QUEUE_DISPATCH_TYPE { 
  WdfIoQueueDispatchSequential  = 1,
  WdfIoQueueDispatchParallel    = 2,
  WdfIoQueueDispatchManual      = 3,
  WdfIoQueueDispatchMaximum     = ( WdfIoQueueDispatchManual + 1 )
} WDF_IO_QUEUE_DISPATCH_TYPE;
````

## Constants

<table>
            
                <tr>
                    <td>WdfIoQueueDispatchManual</td>
                    <td>The framework places requests into the queue but does not deliver them to the driver. The driver must call the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a> method to retrieve a request from the queue.</td>
                </tr>
            
                <tr>
                    <td>WdfIoQueueDispatchMaximum</td>
                    <td>Valid enumeration values were exceeded.</td>
                </tr>
            
                <tr>
                    <td>WdfIoQueueDispatchParallel</td>
                    <td>The framework presents requests to the driver's I/O queue callback functions as soon as the requests are available.</td>
                </tr>
            
                <tr>
                    <td>WdfIoQueueDispatchSequential</td>
                    <td>The I/O queue's requests are presented to the driver's I/O queue callback functions one at a time. The framework delivers the next request after the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a> method to complete the current request.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | wudfddi_types.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558967">IWDFIoQueue::RetrieveNextRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff559070">IWDFIoRequest::Complete</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_DISPATCH_TYPE enumeration%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>