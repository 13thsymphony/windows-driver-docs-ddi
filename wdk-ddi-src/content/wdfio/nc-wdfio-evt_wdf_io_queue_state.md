---
UID: NC:wdfio.EVT_WDF_IO_QUEUE_STATE
title: EVT_WDF_IO_QUEUE_STATE
author: windows-driver-content
description: A driver's EvtIoQueueState event callback function delivers queue state information to the driver.
old-location: wdf\evtioqueuestate.htm
old-project: wdf
ms.assetid: 14999036-c137-4056-b6f7-53a8476fd385
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.evtioqueuestate, EvtIoQueueState callback function, EvtIoQueueState, EVT_WDF_IO_QUEUE_STATE, EVT_WDF_IO_QUEUE_STATE, wdfio/EvtIoQueueState, DFQueueObjectRef_726524eb-d12b-451c-aa6e-3f60aa9b7940.xml, kmdf.evtioqueuestate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdfio.h
req.include-header: Wdf.h
req.target-type: Universal
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
-	UserDefined
apilocation:
-	Wdfio.h
apiname:
-	EvtIoQueueState
product: Windows
targetos: Windows
req.typenames: "*PWDF_INTERRUPT_INFO, WDF_INTERRUPT_INFO"
req.product: Windows 10 or later.
---


# EVT_WDF_IO_QUEUE_STATE function
<p class="CCE_Message">[Applies to KMDF and UMDF]

A driver's <i>EvtIoQueueState</i> event callback function delivers queue state information to the driver.

## Syntax

```
EVT_WDF_IO_QUEUE_STATE EvtWdfIoQueueState;

void EvtWdfIoQueueState(
  WDFQUEUE Queue,
  WDFCONTEXT Context
)
{...}
```

## Parameters

`Queue`

A handle to an I/O queue object.

`Context`

Driver-defined context information that the driver specified when it registered the <i>EvtIoQueueState</i> callback function.


## Return Value

None

## Remarks

Drivers can register an <i>EvtIoQueueState</i> callback function by specifying its address as input to <a href="..\wdfio\nf-wdfio-wdfioqueuestop.md">WdfIoQueueStop</a>, <a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a>, <a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>, or <a href="..\wdfio\nf-wdfio-wdfioqueuereadynotify.md">WdfIoQueueReadyNotify</a>. The framework calls the <i>EvtIoQueueState</i> callback function after the specified operation completes. 

The <i>EvtIoQueueState</i> callback function can be called at IRQL &lt;= DISPATCH_LEVEL, unless the <b>ExecutionLevel</b> member of the device or driver's <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure is set to <b>WdfExecutionLevelPassive</b>.

If the IRQL is PASSIVE_LEVEL, the framework calls the callback function within a <a href="https://msdn.microsoft.com/3781498a-45e9-4f24-8fd2-830eed61298c">critical region</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Universal |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | wdfio.h (include Wdf.h) |
| **IRQL** | "<= DISPATCH_LEVEL (see Remarks section)" |

## See Also

<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuedrain.md">WdfIoQueueDrain</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuereadynotify.md">WdfIoQueueReadyNotify</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuepurge.md">WdfIoQueuePurge</a>

<a href="..\wdfio\nf-wdfio-wdfioqueuestop.md">WdfIoQueueStop</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20EVT_WDF_IO_QUEUE_STATE callback function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>