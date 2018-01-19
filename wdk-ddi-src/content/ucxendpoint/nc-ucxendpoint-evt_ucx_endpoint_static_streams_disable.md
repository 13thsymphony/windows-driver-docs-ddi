---
UID : NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
title : EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
author : windows-driver-content
description : The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.
old-location : buses\evt_ucx_endpoint_static_streams_disable.htm
old-project : usbref
ms.assetid : 79da55ac-61de-40cc-b25b-421f7637a9fe
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS, UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : ucxendpoint.h
req.include-header : Ucxclass.h, Ucxendpoint.h
req.target-type : Windows
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 1.0
req.umdf-ver : 2.0
req.alt-api : PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE
req.alt-loc : ucxendpoint.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : DISPATCH_LEVEL
req.typenames : UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product : Windows 10 or later.
---


# EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE function
The client driver's implementation that UCX calls to release controller resources for all streams for an endpoint.

## Syntax

```
EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE EvtUcxEndpointStaticStreamsDisable;

void EvtUcxEndpointStaticStreamsDisable(
  UCXENDPOINT UcxEndpoint,
  UCXSSTREAMS UcxStaticStreams,
  WDFREQUEST Request
)
{...}
```

## Parameters

`UcxEndpoint`



`UcxStaticStreams`

A handle to a UCX object that represents the static streams.

`Request`

Contains the URB for the <b>URB_FUNCTION_CLOSE_STATIC_STREAMS</b>.


## Return Value

This callback function does not return a value.

## Remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.

The client driver returns completion status in <i>Request</i> and in the USBD_STATUS
    in the URB header.  The driver can complete the WDFREQUEST asynchronously.</p>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |
| **Library** |  |
| **IRQL** | DISPATCH_LEVEL |
| **DDI compliance rules** |  |