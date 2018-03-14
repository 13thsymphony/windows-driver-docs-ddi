---
UID: NF:wdfio.WDF_IO_QUEUE_PURGED
title: WDF_IO_QUEUE_PURGED function
author: windows-driver-content
description: The WDF_IO_QUEUE_PURGED function returns TRUE if an I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_purged.htm
old-project: wdf
ms.assetid: dbb061a6-a770-411c-9c3a-8453662b4362
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFQueueObjectRef_2d745708-c310-494a-aedc-362bdc930650.xml, WDF_IO_QUEUE_PURGED, WDF_IO_QUEUE_PURGED function, kmdf.wdf_io_queue_purged, wdf.wdf_io_queue_purged, wdfio/WDF_IO_QUEUE_PURGED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: None
req.dll: 
req.irql: Any IRQL.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	None
-	None.dll
api_name:
-	WDF_IO_QUEUE_PURGED
product: Windows
targetos: Windows
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---


# WDF_IO_QUEUE_PURGED function
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_PURGED</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is drained.

## Syntax

````
BOOLEAN WDF_IO_QUEUE_PURGED(
  _In_ WDF_IO_QUEUE_STATE State
);
````

## Parameters

`State`

A <a href="..\wdfio\ne-wdfio-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>-typed value that <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a> returns.


## Return Value

<b>WDF_IO_QUEUE_PURGED</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is purged. Otherwise, the function returns <b>FALSE</b>.

## Remarks

An I/O queue is purged if the queue is empty and not accepting new I/O requests, and if all requests that were in the queue have been canceled.

Your driver can call <b>WDF_IO_QUEUE_PURGED</b> after it has called <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="..\wdfio\ne-wdfio-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>.


#### Examples

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is purged.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>BOOLEAN
IsQueuePurged(
    IN WDFQUEUE Queue
    )
{
    WDF_IO_QUEUE_STATE queueStatus;
    queueStatus = WdfIoQueueGetState(
                                     Queue,
                                     NULL,
                                     NULL
                                     );
    return (WDF_IO_QUEUE_PURGED(queueStatus)) ? TRUE : FALSE;
}</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Header** | wdfio.h (include Wdf.h) |
| **Library** | None |
| **IRQL** | Any IRQL. |

## See Also

<a href="..\wdfio\nf-wdfio-wdf_io_queue_drained.md">WDF_IO_QUEUE_DRAINED</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_ready.md">WDF_IO_QUEUE_READY</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_stopped.md">WDF_IO_QUEUE_STOPPED</a>



<a href="..\wdfio\nf-wdfio-wdf_io_queue_idle.md">WDF_IO_QUEUE_IDLE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_PURGED function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>