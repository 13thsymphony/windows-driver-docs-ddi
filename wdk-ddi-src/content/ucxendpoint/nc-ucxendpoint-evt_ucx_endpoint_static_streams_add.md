---
UID: NC:ucxendpoint.EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
title: EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
author: windows-driver-content
description: The client driver's implementation that UCX calls to create static streams.
old-location: buses\evt_ucx_endpoint_static_streams_add.htm
old-project: usbref
ms.assetid: 76f94f19-894a-47af-a407-8e14263f1143
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.evt_ucx_endpoint_static_streams_add, EvtUcxEndpointStaticStreamsAdd callback function [Buses], EvtUcxEndpointStaticStreamsAdd, EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD, EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD, ucxendpoint/EvtUcxEndpointStaticStreamsAdd, PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD callback function pointer [Buses], PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ucxendpoint.h
apiname:
-	PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---


# EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD function
The client driver's implementation that UCX calls to create static streams.

## Syntax

```
EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD EvtUcxEndpointStaticStreamsAdd;

NTSTATUS EvtUcxEndpointStaticStreamsAdd(
  UCXENDPOINT UcxEndpoint,
  ULONG NumberOfStreams,
  PUCXSSTREAMS_INIT UcxStaticStreamsInit
)
{...}
```

## Parameters

`UcxEndpoint`



`NumberOfStreams`

The number of non-default streams to create.

`UcxStaticStreamsInit`

A pointer to an opaque structure containing
        initialization information.  This structure is managed by UCX.


## Return Value

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. Otherwise it must return a status value for which NT_SUCCESS(status) equals FALSE.

## Remarks

The UCX client driver registers this callback function with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.

This callback function creates a UCX static streams object by calling the <a href="..\ucxsstreams\nf-ucxsstreams-ucxstaticstreamscreate.md">UcxStaticStreamsCreate</a>
 method. Only one UCX static streams object can be associated with a single endpoint.  The driver then calls <a href="..\ucxsstreams\nf-ucxsstreams-ucxstaticstreamssetstreaminfo.md">UcxStaticStreamsSetStreamInfo</a>
 once per stream to create a queue for each stream.

A static streams object is not enabled
    until UCX calls the client driver's <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback function.


#### Examples

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
Endpoint_EvtEndpointStaticStreamsAdd(
    UCXENDPOINT         UcxEndpoint,
    ULONG               NumberOfStreams,
    PUCXSSTREAMS_INIT   UcxStaticStreamsInit
    )
{
    NTSTATUS                    status;
    WDF_OBJECT_ATTRIBUTES       wdfAttributes;
    UCXSSTREAMS                 ucxStaticStreams;
    STREAM_INFO                 streamInfo;
    ULONG                       streamId;

    TRY {

        WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&amp;wdfAttributes, STATIC_STREAMS_CONTEXT);

        status = UcxStaticStreamsCreate(UcxEndpoint,
                                        &amp;UcxStaticStreamsInit,
                                        &amp;wdfAttributes,
                                        &amp;ucxStaticStreams);
        // … error handling …

        for (i = 0, streamId = 1; i &lt; NumberOfStreams; i += 1, streamId += 1) {

            // … create WDF queue …

            STREAM_INFO_INIT(&amp;streamInfo,
                             wdfQueue,
                             streamId);

            UcxStaticStreamsSetStreamInfo(ucxStaticStreams, &amp;streamInfo);
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
| **IRQL** | PASSIVE_LEVEL |