---
UID: NC:ucxendpoint.EVT_UCX_DEFAULT_ENDPOINT_UPDATE
title: EVT_UCX_DEFAULT_ENDPOINT_UPDATE
author: windows-driver-content
description: The client driver's implementation that UCX calls with information about the default endpoint.
old-location: buses\evt_ucx_default_endpoint_update.htm
old-project: usbref
ms.assetid: 0a67ef0a-07ec-43d3-9a25-b28192677b35
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.evt_ucx_default_endpoint_update, EvtUcxDefaultEndpointUpdate callback function [Buses], EvtUcxDefaultEndpointUpdate, EVT_UCX_DEFAULT_ENDPOINT_UPDATE, EVT_UCX_DEFAULT_ENDPOINT_UPDATE, ucxendpoint/EvtUcxDefaultEndpointUpdate, PEVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function pointer [Buses], PEVT_UCX_DEFAULT_ENDPOINT_UPDATE
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ucxendpoint.h
apiname:
-	PEVT_UCX_DEFAULT_ENDPOINT_UPDATE
product: Windows
targetos: Windows
req.typenames: UCX_CONTROLLER_TRANSPORT_CHARACTERISTICS_CHANGE_FLAGS
req.product: Windows 10 or later.
---


# EVT_UCX_DEFAULT_ENDPOINT_UPDATE function
The client driver's implementation that UCX calls with information about the default endpoint.

## Syntax

```
EVT_UCX_DEFAULT_ENDPOINT_UPDATE EvtUcxDefaultEndpointUpdate;

void EvtUcxDefaultEndpointUpdate(
  UCXCONTROLLER UcxController,
  WDFREQUEST Request
)
{...}
```

## Parameters

`UcxController`

A handle to the UCX controller that the client driver received in a previous call to  the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188033">UcxControllerCreate</a> method.

`Request`

A <a href="..\ucxendpoint\ns-ucxendpoint-_default_endpoint_update.md">DEFAULT_ENDPOINT_UPDATE</a> structure that contains the handle to the default endpoint to be updated.


## Return Value

This callback function does not return a value.

## Remarks

The UCX client driver registers its <i>EVT_UCX_DEFAULT_ENDPOINT_UPDATE</i> implementation with the USB host controller extension (UCX) by calling the <a href="..\ucxendpoint\nf-ucxendpoint-ucxendpointcreate.md">UcxEndpointCreate</a>
 method.

UCX typically calls this routine to update the default endpoint's maximum packet size.  The client driver returns completion status in the WDFREQUEST, which it can complete
    asynchronously.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Windows |
| **Minimum KMDF version** | 1.0 |
| **Minimum UMDF version** | 2.0 |
| **Header** | ucxendpoint.h (include Ucxclass.h, Ucxendpoint.h) |
| **IRQL** | DISPATCH_LEVEL |

## See Also

<a href="..\ucxendpoint\nf-ucxendpoint-ucxdefaultendpointinitseteventcallbacks.md">UcxDefaultEndpointInitSetEventCallbacks</a>

<a href="..\ucxendpoint\nf-ucxendpoint-ucx_default_endpoint_event_callbacks_init.md">UCX_DEFAULT_ENDPOINT_EVENT_CALLBACKS_INIT</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20EVT_UCX_DEFAULT_ENDPOINT_UPDATE callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>