---
UID: NS:wsk._WSK_CLIENT_DATAGRAM_DISPATCH
title: "_WSK_CLIENT_DATAGRAM_DISPATCH"
author: windows-driver-content
description: The WSK_CLIENT_DATAGRAM_DISPATCH structure specifies a WSK application's dispatch table of event callback functions for a datagram socket.
old-location: netvista\wsk_client_datagram_dispatch.htm
old-project: netvista
ms.assetid: 559a98e0-61fd-4234-a595-e533e7eaafe8
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PWSK_CLIENT_DATAGRAM_DISPATCH, PWSK_CLIENT_DATAGRAM_DISPATCH, PWSK_CLIENT_DATAGRAM_DISPATCH structure pointer [Network Drivers Starting with Windows Vista], WSK_CLIENT_DATAGRAM_DISPATCH, WSK_CLIENT_DATAGRAM_DISPATCH structure [Network Drivers Starting with Windows Vista], _WSK_CLIENT_DATAGRAM_DISPATCH, netvista.wsk_client_datagram_dispatch, wsk/PWSK_CLIENT_DATAGRAM_DISPATCH, wsk/WSK_CLIENT_DATAGRAM_DISPATCH, wskref_131878e6-5665-47e1-9b84-0dcbdecb9444.xml"
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	wsk.h
api_name:
-	WSK_CLIENT_DATAGRAM_DISPATCH
product: Windows
targetos: Windows
req.typenames: WSK_CLIENT_DATAGRAM_DISPATCH, *PWSK_CLIENT_DATAGRAM_DISPATCH
req.product: Windows 10 or later.
---

# _WSK_CLIENT_DATAGRAM_DISPATCH structure
The WSK_CLIENT_DATAGRAM_DISPATCH structure specifies a WSK application's dispatch table of event
  callback functions for a datagram socket.

## Syntax
```
typedef struct _WSK_CLIENT_DATAGRAM_DISPATCH {
  PFN_WSK_RECEIVE_FROM_EVENT WskReceiveFromEvent;
} WSK_CLIENT_DATAGRAM_DISPATCH, *PWSK_CLIENT_DATAGRAM_DISPATCH;
```

## Members


`WskReceiveFromEvent`

A pointer to the WSK application's 
     <a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a> event callback
     function for the socket. If the WSK application does not enable the 
     <i>WskReceiveFromEvent</i> event callback function for the socket, this pointer can be <b>NULL</b>.

## Remarks
A WSK application passes a pointer to a WSK_CLIENT_DATAGRAM_DISPATCH structure to the WSK subsystem
    when the WSK application calls the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a> function to create a datagram
    socket.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available in Windows Vista and later versions of the Windows operating   systems. Available in Windows Vista and later versions of the Windows operating   systems. |
| **Header** | wsk.h (include Wsk.h) |

## See Also

<a href="https://msdn.microsoft.com/fa8d3395-b800-4e5c-af03-b21520f69158">
   WSK_PROVIDER_DATAGRAM_DISPATCH</a>



<a href="https://msdn.microsoft.com/1cdb8a70-54fe-44a6-a16c-71cbf6a49ef2">WskReceiveFromEvent</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff571149">WskSocket</a>