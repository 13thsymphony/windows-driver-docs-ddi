---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_ABORT
title: EVT_UCX_ENDPOINT_ABORT
author: windows-driver-content
description: The client driver's implementation that UCX calls to abort the queue associated with the endpoint.
old-location: buses\evt_ucx_endpoint_abort.htm
old-project: usbref
ms.assetid: b457d0b5-30a2-42f9-9194-8c60af790f75
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: EVT_UCX_ENDPOINT_ABORT, EvtUcxEndpointAbort, EvtUcxEndpointAbort callback function [Buses], PEVT_UCX_ENDPOINT_ABORT, PEVT_UCX_ENDPOINT_ABORT callback function pointer [Buses], buses.evt_ucx_endpoint_abort, ucxendpoint/EvtUcxEndpointAbort
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
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
req.irql: DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ucxendpoint.h
api_name:
-	PEVT_UCX_ENDPOINT_ABORT
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---


# EVT_UCX_ENDPOINT_ABORT callback function
The client driver's implementation that UCX calls to abort the queue associated with the endpoint.

## Syntax

```
EVT_UCX_ENDPOINT_ABORT EvtUcxEndpointAbort;

void EvtUcxEndpointAbort(
  UCXCONTROLLER UcxController,
  UCXENDPOINT UcxEndpoint
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`UcxEndpoint`




## Return Value

This callback function does not return a value.

## Remarks

The client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188039">UcxEndpointCreate</a>
 method.

This function completes all requests associated with the endpoint, typically by calling <a href="https://msdn.microsoft.com/library/windows/hardware/hh439289">WdfIoQueueStopAndPurge</a>.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>VOID
Endpoint_UcxEvtEndpointAbort(
    UCXCONTROLLER   UcxController,
	   UCXENDPOINT     UcxEndpoint
	  )
	{
	            WdfIoQueueStopAndPurge(endpointContext-&gt;WdfQueue,
	                                   Endpoint_WdfEvtAbortComplete,
	                                   UcxEndpoint);
	}
</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |
| **IRQL** | DISPATCH_LEVEL |