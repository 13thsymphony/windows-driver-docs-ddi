---
UID: NC.ucxendpoint.EVT_UCX_ENDPOINT_ABORT
title: EVT_UCX_ENDPOINT_ABORT
author: windows-driver-content
description: The client driver's implementation that UCX calls to abort the queue associated with the endpoint.
old-location: buses\evt_ucx_endpoint_abort.htm
old-project: usbref
ms.assetid: b457d0b5-30a2-42f9-9194-8c60af790f75
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
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
req.alt-api: PEVT_UCX_ENDPOINT_ABORT
req.alt-loc: ucxendpoint.h
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
req.product: Windows 10 or later.
---

# EVT_UCX_ENDPOINT_ABORT callback



## -description
The client driver's implementation that UCX calls to abort the queue associated with the endpoint.


## -prototype

````
EVT_UCX_ENDPOINT_ABORT EvtUcxEndpointAbort;

VOID EvtUcxEndpointAbort(
  _In_ UCXCONTROLLER UcxController,
  _In_ UCXENDPOINT   Endpoint
)
{ ... }

typedef EVT_UCX_ENDPOINT_ABORT PEVT_UCX_ENDPOINT_ABORT;
````


## -parameters

### -param UcxController [in]

 A handle to the UCX controller that the client driver received in a previous call to  the <a href="buses._ucxcontrollercreate">UcxControllerCreate</a> method.

### -param Endpoint [in]

A handle to a UCXENDPOINT object.

## -returns
This callback function does not return a value.

## -remarks
The client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="buses._ucxendpointcreate">UcxEndpointCreate</a>
 method.

This function completes all requests associated with the endpoint, typically by calling <a href="wdf.wdfioqueuestopandpurge">WdfIoQueueStopAndPurge</a>.

## -requirements
<table>
<tr>
<th width="30%">
Minimum KMDF version
</th>
<td width="70%">
1.0
</td>
</tr>
<tr>
<th width="30%">
Minimum UMDF version
</th>
<td width="70%">
2.0
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Ucxendpoint.h (include Ucxclass.h or Ucxendpoint.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL
</th>
<td width="70%">
DISPATCH_LEVEL
</td>
</tr>
</table>