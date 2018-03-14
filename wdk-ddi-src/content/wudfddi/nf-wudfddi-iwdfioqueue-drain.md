---
UID: NF:wudfddi.IWDFIoQueue.Drain
title: IWDFIoQueue::Drain method
author: windows-driver-content
description: The Drain method directs the queue to reject new incoming I/O requests and allow already-queued requests to be delivered to the driver for processing.
old-location: wdf\iwdfioqueue_drain.htm
old-project: wdf
ms.assetid: 0356e8a7-de44-4b0f-9067-ca3bb04260d8
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: Drain method, Drain method, IWDFIoQueue interface, Drain,IWDFIoQueue.Drain, IWDFIoQueue, IWDFIoQueue interface, Drain method, IWDFIoQueue::Drain, UMDFQueueObjectRef_cb7bdc3f-3280-4949-a60a-b78f13492da9.xml, umdf.iwdfioqueue_drain, wdf.iwdfioqueue_drain, wudfddi/IWDFIoQueue::Drain
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
-	IWDFIoQueue.Drain
product: Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# Drain method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>Drain</b> method directs the queue to reject new incoming I/O requests and allow already-queued requests to be delivered to the driver for processing.

## Syntax

````
void Drain(
  [in, optional] IQueueCallbackStateChange *pDrainComplete
);
````

## Parameters

`pDrainComplete`

A pointer to the <a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a> interface whose method the framework calls to deliver queue state to the driver. The framework calls the method after all requests are completed or canceled and the queue is empty. This parameter is optional and can be <b>NULL</b>.


## Return Value

None

## Remarks

A driver should ensure that only one of the following methods is in progress at any given time: 

<ul>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a>


</li>
<li>
<b>IWDFIoQueue::Drain</b>

</li>
<li>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558962">IWDFIoQueue::Purge</a>


</li>
</ul>
For example, if the driver previously called <b>Drain</b>, it should wait for notification from the method of the interface that the <i>pDrainComplete</i> parameter points to before the driver calls either <a href="https://msdn.microsoft.com/library/windows/hardware/dn927275">Stop</a> or <a href="https://msdn.microsoft.com/c7863713-850f-4516-aec5-9e851c36cf52">Purge</a>. Violating this rule results in termination of the host process.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **End of support** | Unavailable in UMDF 2.0 and later.  |
| **Target Platform** | Desktop |
| **Minimum UMDF version** | 1.5 |
| **Header** | wudfddi.h (include Wudfddi.h) |
| **DLL** | WUDFx.dll |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff558962">IWDFIoQueue::Purge</a>



<a href="..\wudfddi\nn-wudfddi-iqueuecallbackstatechange.md">IQueueCallbackStateChange</a>



<a href="..\wudfddi\nn-wudfddi-iwdfioqueue.md">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558980">IWDFIoQueue::Stop</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20IWDFIoQueue::Drain method%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>