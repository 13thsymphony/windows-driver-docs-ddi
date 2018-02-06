---
UID: NS:ucxendpoint._UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
title: "_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS"
author: windows-driver-content
description: This structure provides a list of UCX default endpoint event callback functions.
old-location: buses\_ucx_default_endpoint_event_callbacks.htm
old-project: usbref
ms.assetid: A22E96FC-E219-4F6C-B8AF-AC86FAD89543
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure pointer [Buses], *PUCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, ucxendpoint/P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure [Buses], ucxendpoint/_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, buses._ucx_default_endpoint_event_callbacks
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
-	UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS
product: Windows
targetos: Windows
req.typenames: "*PUCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS"
req.product: Windows 10 or later.
---

# _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure
This structure provides a list of UCX default endpoint event callback functions.

## Syntax
````
typedef struct _UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS {
  ULONG                                    Size;
  PEVT_UCX_ENDPOINT_PURGE                  EvtEndpointPurge;
  PEVT_UCX_ENDPOINT_START                  EvtEndpointStart;
  PEVT_UCX_ENDPOINT_ABORT                  EvtEndpointAbort;
  PEVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS EvtEndpointOkToCancelTransfers;
  PEVT_UCX_DEFAULT_ENDPOINT_UPDATE         EvtDefaultEndpointUpdate;
  HANDLE                                   Reserved1;
} UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS, *P_UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS;
````

## Members


`EvtDefaultEndpointUpdate`

A pointer to a EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function.

`EvtEndpointAbort`

A pointer to a EVT_UCX_ENDPOINT_ABORT callback function.

`EvtEndpointOkToCancelTransfers`

A pointer to a EVT_UCX_ENDPOINT_OK_TO_CANCEL_TRANSFERS callback function.

`EvtEndpointPurge`

A pointer to a EVT_UCX_ENDPOINT_PURGE callback function.

`EvtEndpointStart`

A pointer to a EVT_UCX_ENDPOINT_START callback function.

`Reserved1`

Do not use.

`Size`

The size in bytes of this structure.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |

## See Also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks.md">UcxDefaultEndpointInitSetEventCallbacks</a>

<a href="..\ucxendpoint\nf-ucxendpoint-ucx_default_endpoint_event_callbacks_init.md">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>