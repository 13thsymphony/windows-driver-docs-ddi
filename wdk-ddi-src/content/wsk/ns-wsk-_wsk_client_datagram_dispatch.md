---
UID: NS.WSK._WSK_CLIENT_DATAGRAM_DISPATCH
title: _WSK_CLIENT_DATAGRAM_DISPATCH
author: windows-driver-content
description: The WSK_CLIENT_DATAGRAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a datagram socket.
old-location: netvista\wsk_client_datagram_dispatch.htm
old-project: netvista
ms.assetid: 559a98e0-61fd-4234-a595-e533e7eaafe8
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WSK_CLIENT_DATAGRAM_DISPATCH, *PWSK_CLIENT_DATAGRAM_DISPATCH, WSK_CLIENT_DATAGRAM_DISPATCH
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wsk.h
req.include-header: Wsk.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating   systems.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WSK_CLIENT_DATAGRAM_DISPATCH
req.alt-loc: wsk.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# _WSK_CLIENT_DATAGRAM_DISPATCH structure



## -description
The WSK_CLIENT_DATAGRAM_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a datagram socket.


## -syntax

````
typedef struct _WSK_CLIENT_DATAGRAM_DISPATCH {
  PFN_WSK_RECEIVE_FROM_EVENT WskReceiveFromEvent;
} WSK_CLIENT_DATAGRAM_DISPATCH, *PWSK_CLIENT_DATAGRAM_DISPATCH;
````


## -struct-fields

### -field WskReceiveFromEvent

A pointer to the WSK application's 
     <a href="..\wsk\nc-wsk-pfn_wsk_receive_from_event.md">WskReceiveFromEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskReceiveFromEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

## -remarks
A WSK application passes a pointer to a WSK_CLIENT_DATAGRAM_DISPATCH structure to the WSK subsystem
    when the WSK application calls the 
    <a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a> function to create a datagram
    socket.

## -requirements
<table>
<tr>
<th width="30%">
Version
</th>
<td width="70%">
Available in Windows Vista and later versions of the Windows operating
   systems.
</td>
</tr>
<tr>
<th width="30%">
Header
</th>
<td width="70%">
<dl>
<dt>Wsk.h (include Wsk.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_socket.md">WskSocket</a>
</dt>
<dt>
<a href="..\wsk\nc-wsk-pfn_wsk_receive_from_event.md">WskReceiveFromEvent</a>
</dt>
<dt>
<a href="netvista.wsk_provider_datagram_dispatch">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WSK_CLIENT_DATAGRAM_DISPATCH structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
