---
UID: NF:wudfddi.IQueueCallbackStateChange.OnStateChange
title: IQueueCallbackStateChange::OnStateChange method
author: windows-driver-content
description: The OnStateChange method is called when the state of the I/O queue object changes.
old-location: wdf\iqueuecallbackstatechange_onstatechange.htm
old-project: wdf
ms.assetid: 69a422a1-b878-496e-b1b9-e04b7c3db121
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: IQueueCallbackStateChange, IQueueCallbackStateChange interface, OnStateChange method, IQueueCallbackStateChange::OnStateChange, OnStateChange method, OnStateChange method, IQueueCallbackStateChange interface, OnStateChange,IQueueCallbackStateChange.OnStateChange, UMDFQueueObjectRef_194f5013-22a2-40c4-8913-9371aa281009.xml, umdf.iqueuecallbackstatechange_onstatechange, wdf.iqueuecallbackstatechange_onstatechange, wudfddi/IQueueCallbackStateChange::OnStateChange
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: wudfddi.h
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	COM
api_location:
-	Wudfddi.h
api_name:
-	IQueueCallbackStateChange.OnStateChange
product:
- Windows
targetos: Windows
req.typenames: POWER_ACTION, *PPOWER_ACTION
req.product: Windows 10 or later.
---


# IQueueCallbackStateChange::OnStateChange method
<p class="CCE_Message">[<b>Warning:</b> UMDF 2 is the latest version of UMDF and supersedes UMDF 1.  All new UMDF drivers should be written using UMDF 2.  No new features are being added to UMDF 1 and there is limited support for UMDF 1 on newer versions of Windows 10.  Universal Windows drivers must use UMDF 2.  For more info, see <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/getting-started-with-umdf-version-2">Getting Started with UMDF</a>.]

The <b>OnStateChange</b> method is called when the state of the I/O queue object changes.

## Syntax

```
void OnStateChange(
  IWDFIoQueue        *pWdfQueue,
  WDF_IO_QUEUE_STATE QueueState
);
```

## Parameters

`pWdfQueue`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a> interface for the I/O queue object whose state changes.

`QueueState`

A valid bitwise OR of <a href="https://msdn.microsoft.com/library/windows/hardware/ff561417">WDF_IO_QUEUE_STATE</a>-typed values that indicates status for the queue.


## Return Value

None

## Remarks

A driver registers the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556877">IQueueCallbackStateChange</a> interface when the driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a> method to create an I/O queue or to configure the default I/O queue. The driver can optionally register the <b>IQueueCallbackStateChange</b> interface only for a manual queue. The driver must not register <b>IQueueCallbackStateChange</b> for a sequential or a parallel queue.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Header** | wudfddi.h (include Wudfddi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff556877">IQueueCallbackStateChange</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557020">IWDFDevice::CreateIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff558943">IWDFIoQueue</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561417">WDF_IO_QUEUE_STATE</a>