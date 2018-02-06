---
UID: NC:ndkpi.NDK_FN_CONTROL_CONNECT_EVENTS
title: NDK_FN_CONTROL_CONNECT_EVENTS
author: windows-driver-content
description: The NdkControlConnectEvents (NDK_FN_CONTROL_CONNECT_EVENTS) function pauses and restarts NDK connect event callback functions.
old-location: netvista\ndk_fn_control_connect_events.htm
old-project: netvista
ms.assetid: 3AA50940-A782-4A46-8E45-077BC76D41A7
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndk_fn_control_connect_events, NdkControlConnectEvents callback function [Network Drivers Starting with Windows Vista], NdkControlConnectEvents, NDK_FN_CONTROL_CONNECT_EVENTS, NDK_FN_CONTROL_CONNECT_EVENTS, ndkpi/NdkControlConnectEvents
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: ndkpi.h
req.include-header: Ndkpi.h
req.target-type: Windows
req.target-min-winverclnt: None supported,Supported in NDIS 6.30 and later.
req.target-min-winversvr: Windows Server 2012
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndkpi.h
apiname:
-	NdkControlConnectEvents
product: Windows
targetos: Windows
req.typenames: "*PNDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS"
---


# NDK_FN_CONTROL_CONNECT_EVENTS callback function
The <i>NdkControlConnectEvents</i> (<i>NDK_FN_CONTROL_CONNECT_EVENTS</i>) function pauses and restarts NDK connect event callback functions.

## Syntax

```
NDK_FN_CONTROL_CONNECT_EVENTS NdkFnControlConnectEvents;

void NdkFnControlConnectEvents(
  NDK_LISTENER *pNdkListener,
  BOOLEAN Pause
)
{...}
```

## Parameters

`*pNdkListener`

A pointer to an NDK listener object (<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>).

`Pause`

A BOOLEAN value that specifies if a connection is paused or restarted. If <i>Pause</i> is TRUE the connection is paused. If <i>Pause</i> is FALSE the connection is restarted.


## Return Value

None

## Remarks

This function is closely related to the <i>NdkConnectEventCallback</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>) function. The  <i>NDK_FN_CONNECT_EVENT_CALLBACK</i> function is called by an NDK provider to notify a consumer about an incoming connection request.
To pause the reception of connect event callbacks, an  NDK consumer can pass TRUE in the <i>Pause</i> parameter.  When a connection is  paused, the incoming connection requests must be treated as if there is no NDK listener  (<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>) on the targeted address.

To restart  the reception of connect event callbacks, the consumer passes FALSE in the <i>Pause</i> parameter.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | None supported,Supported in NDIS 6.30 and later. None supported,Supported in NDIS 6.30 and later. |
| **Target Platform** | Windows |
| **Header** | ndkpi.h (include Ndkpi.h) |
| **IRQL** | "<=DISPATCH_LEVEL" |

## See Also

<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>

<a href="..\ndkpi\ns-ndkpi-_ndk_listener.md">NDK_LISTENER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDK_FN_CONTROL_CONNECT_EVENTS callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>