---
UID: NC.ndkpi.NDK_FN_CONTROL_CONNECT_EVENTS
title: NDK_FN_CONTROL_CONNECT_EVENTS
author: windows-driver-content
description: The NdkControlConnectEvents (NDK_FN_CONTROL_CONNECT_EVENTS) function pauses and restarts NDK connect event callback functions.
old-location: netvista\ndk_fn_control_connect_events.htm
old-project: NetVista
ms.assetid: 3AA50940-A782-4A46-8E45-077BC76D41A7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _NDIS_WWAN_VISIBLE_PROVIDERS, NDIS_WWAN_VISIBLE_PROVIDERS, *PNDIS_WWAN_VISIBLE_PROVIDERS, PNDIS_WWAN_VISIBLE_PROVIDERS
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
req.alt-api: NdkControlConnectEvents
req.alt-loc: ndkpi.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <=DISPATCH_LEVEL
---

# NDK_FN_CONTROL_CONNECT_EVENTS callback



## -description
The <i>NdkControlConnectEvents</i> (<i>NDK_FN_CONTROL_CONNECT_EVENTS</i>) function pauses and restarts NDK connect event callback functions.



## -prototype

````
NDK_FN_CONTROL_CONNECT_EVENTS NdkControlConnectEvents;

VOID NdkControlConnectEvents(
  _In_ NDK_LISTENER *pNdkListener,
  _In_ BOOLEAN      Pause
)
{ ... }
````


## -parameters

### -param pNdkListener [in]

A pointer to an NDK listener object (<a href="netvista.ndk_listener">NDK_LISTENER</a>).


### -param Pause [in]

A BOOLEAN value that specifies if a connection is paused or restarted. If <i>Pause</i> is TRUE the connection is paused. If <i>Pause</i> is FALSE the connection is restarted.


## -returns
None


## -remarks
This function is closely related to the <i>NdkConnectEventCallback</i> (<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>) function. The  <i>NDK_FN_CONNECT_EVENT_CALLBACK</i> function is called by an NDK provider to notify a consumer about an incoming connection request.
To pause the reception of connect event callbacks, an  NDK consumer can pass TRUE in the <i>Pause</i> parameter.  When a connection is  paused, the incoming connection requests must be treated as if there is no NDK listener  (<a href="netvista.ndk_listener">NDK_LISTENER</a>) on the targeted address.

To restart  the reception of connect event callbacks, the consumer passes FALSE in the <i>Pause</i> parameter.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
None supported

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2012

</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Supported in NDIS 6.30 and later.

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Ndkpi.h (include Ndkpi.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;=DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndk_listener">NDK_LISTENER</a>
</dt>
<dt>
<a href="..\ndkpi\nc-ndkpi-ndk_fn_connect_event_callback.md">NDK_FN_CONNECT_EVENT_CALLBACK</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDK_FN_CONTROL_CONNECT_EVENTS callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

