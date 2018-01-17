---
UID: NF:wdfio.WDF_IO_QUEUE_READY
title: WDF_IO_QUEUE_READY function
author: windows-driver-content
description: The WDF_IO_QUEUE_READY function returns TRUE if an I/O queue's state indicates that the queue is drained.
old-location: wdf\wdf_io_queue_ready.htm
old-project: wdf
ms.assetid: 622e09eb-37ae-403e-9d18-acf2e7761b43
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: WDF_IO_QUEUE_READY
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
req.alt-api: WDF_IO_QUEUE_READY
req.alt-loc: None,None.dll
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
req.typenames: WDF_IO_QUEUE_STATE
req.product: Windows 10 or later.
---

# WDF_IO_QUEUE_READY function



## -description
<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WDF_IO_QUEUE_READY</b> function returns <b>TRUE</b> if an I/O queue's state indicates that the queue is drained.



## -syntax

````
BOOLEAN WDF_IO_QUEUE_READY(
  _In_ WDF_IO_QUEUE_STATE State
);
````


## -parameters

### -param State [in]

A <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>-typed value that <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a> returns.


## -returns
<b>WDF_IO_QUEUE_READY</b> returns <b>TRUE</b> if the specified queue state indicates that the queue is ready. Otherwise, the function returns <b>FALSE</b>.


## -remarks
An I/O queue is ready if the queue can accept and dispatch I/O requests.

Your driver can call <b>WDF_IO_QUEUE_READY</b> after it has called <a href="..\wdfio\nf-wdfio-wdfioqueuegetstate.md">WdfIoQueueGetState</a>.

For more information about I/O queue states, see <a href="..\wudfddi_types\ne-wudfddi_types-_wdf_io_queue_state.md">WDF_IO_QUEUE_STATE</a>.

The following code example is a routine that returns <b>TRUE</b> if a specified I/O queue is ready.


## -see-also
<dl>
<dt>
<a href="..\wdfio\nf-wdfio-wdf_io_queue_drained.md">WDF_IO_QUEUE_DRAINED</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdf_io_queue_idle.md">WDF_IO_QUEUE_IDLE</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdf_io_queue_purged.md">WDF_IO_QUEUE_PURGED</a>
</dt>
<dt>
<a href="..\wdfio\nf-wdfio-wdf_io_queue_stopped.md">WDF_IO_QUEUE_STOPPED</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WDF_IO_QUEUE_READY function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

