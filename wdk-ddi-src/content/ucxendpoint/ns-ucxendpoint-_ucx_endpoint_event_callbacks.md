---
UID: NS:ucxendpoint._UCX_ENDPOINT_EVENT_CALLBACKS
title: "_UCX_ENDPOINT_EVENT_CALLBACKS"
author: windows-driver-content
description: This structure provides a list of pointers to UCX endpoint event callback functions.
old-location: buses\_ucx_endpoint_event_callbacks.htm
old-project: UsbRef
ms.assetid: 93071B7B-74D8-44A2-984D-A6BABFC07BA3
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UCX_ENDPOINT_EVENT_CALLBACKS structure [Buses], _UCX_ENDPOINT_EVENT_CALLBACKS, P_UCX_ENDPOINT_EVENT_CALLBACKS, P_UCX_ENDPOINT_EVENT_CALLBACKS structure pointer [Buses], ucxendpoint/P_UCX_ENDPOINT_EVENT_CALLBACKS, UCX_ENDPOINT_EVENT_CALLBACKS, buses._ucx_endpoint_event_callbacks, ucxendpoint/_UCX_ENDPOINT_EVENT_CALLBACKS, *PUCX_ENDPOINT_EVENT_CALLBACKS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxendpoint.h
req.include-header: Ucxclass.h, Ucxendpoint.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxendpoint.h
apiname:
-	UCX_ENDPOINT_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: "*PUCX_ENDPOINT_EVENT_CALLBACKS, UCX_ENDPOINT_EVENT_CALLBACKS"
req.product: Windows 10 or later.
---

# _UCX_ENDPOINT_EVENT_CALLBACKS structure
This structure provides a list of  pointers to UCX endpoint event callback functions.

## Syntax
````
typedef struct _UCX_ENDPOINT_EVENT_CALLBACKS {
  ULONG                                           Size;
  PEVT_UCX_ENDPOINT_PURGE                         EvtEndpointPurge;
  PEVT_UCX_ENDPOINT_START                         EvtEndpointStart;
  PEVT_UCX_ENDPOINT_ABORT                         EvtEndpointAbort;
  PEVT_UCX_ENDPOINT_RESET                         EvtEndpointReset;
  PEVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS        EvtEndpointOkToCancelTransfers;
  PEVT_UCX_ENDPOINT_STATIC_STREAMS_ADD            EvtEndpointStaticStreamsAdd;
  PEVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE         EvtEndpointStaticStreamsEnable;
  PEVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE        EvtEndpointStaticStreamsDisable;
  HANDLE                                          Reserved1;
  PFN_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS EvtEndpointGetIsochTransferPathDelays;
  PFN_UCX_ENDPOINT_SET_CHARACTERISTIC             EvtEndpointSetCharacteristic;
} UCX_ENDPOINT_EVENT_CALLBACKS, *P_UCX_ENDPOINT_EVENT_CALLBACKS;
````

## Members


`EvtEndpointAbort`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_abort.md">EVT_UCX_ENDPOINT_ABORT</a> callback function.

`EvtEndpointGetIsochTransferPathDelays`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_get_isoch_transfer_path_delays.md">EVT_UCX_ENDPOINT_GET_ISOCH_TRANSFER_PATH_DELAYS</a> callback function.

`EvtEndpointOkToCancelTransfers`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_ok_to_cancel_transfers.md">EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS</a> callback function.

`EvtEndpointPurge`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_purge.md">EVT_UCX_ENDPOINT_PURGE</a> callback function.

`EvtEndpointReset`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_reset.md">EVT_UCX_ENDPOINT_RESET</a> callback function.

`EvtEndpointSetCharacteristic`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_set_characteristic.md">EVT_UCX_ENDPOINT_SET_CHARACTERISTIC</a> callback function.

`EvtEndpointStart`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_start.md">EVT_UCX_ENDPOINT_START</a> callback function.

`EvtEndpointStaticStreamsAdd`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_add.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_ADD</a> callback function.

`EvtEndpointStaticStreamsDisable`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_disable.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_DISABLE</a> callback function.

`EvtEndpointStaticStreamsEnable`

A pointer to an <a href="..\ucxendpoint\nc-ucxendpoint-evt_ucx_endpoint_static_streams_enable.md">EVT_UCX_ENDPOINT_STATIC_STREAMS_ENABLE</a> callback function.

`Reserved1`

Do not use.

`Size`

The size in bytes of the structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |

## See Also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointinitseteventcallbacks.md">UcxEndpointInitSetEventCallbacks</a>



<a href="..\ucxendpoint\nf-ucxendpoint-ucx_endpoint_event_callbacks_init.md">UCX_ENDPOINT_EVENT_CALLBACKS_INIT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UCX_ENDPOINT_EVENT_CALLBACKS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>