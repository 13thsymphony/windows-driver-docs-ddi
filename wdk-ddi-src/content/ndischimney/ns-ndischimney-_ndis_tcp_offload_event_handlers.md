---
UID: NS:ndischimney._NDIS_TCP_OFFLOAD_EVENT_HANDLERS
title: "_NDIS_TCP_OFFLOAD_EVENT_HANDLERS"
author: windows-driver-content
description: The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for the TCP chimney.
old-location: netvista\ndis_tcp_offload_event_handlers.htm
old-project: netvista
ms.assetid: 72863a3e-9907-43e1-ad83-831a972ab823
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, NDIS_TCP_OFFLOAD_EVENT_HANDLERS, NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure [Network Drivers Starting with Windows Vista], PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, PNDIS_TCP_OFFLOAD_EVENT_HANDLERS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/NDIS_TCP_OFFLOAD_EVENT_HANDLERS, ndischimney/PNDIS_TCP_OFFLOAD_EVENT_HANDLERS, netvista.ndis_tcp_offload_event_handlers, tcp_chim_struct_ae670e4d-ac1a-4dd2-95f5-2f2b202003e4.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndischimney.h
req.include-header: Ndischimney.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndischimney.h
api_name:
-	NDIS_TCP_OFFLOAD_EVENT_HANDLERS
product:
- Windows
targetos: Windows
req.typenames: NDIS_TCP_OFFLOAD_EVENT_HANDLERS, *PNDIS_TCP_OFFLOAD_EVENT_HANDLERS
---

# _NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure contains the entry points for the NDIS functions for
  the TCP chimney.

## Syntax
```
typedef struct _NDIS_TCP_OFFLOAD_EVENT_HANDLERS {
  NDIS_OBJECT_HEADER                   Header;
  NDIS_TCP_OFFLOAD_EVENT_INDICATE      NdisTcpOffloadEventHandler;
  NDIS_TCP_OFFLOAD_RECEIVE_INDICATE    NdisTcpOffloadReceiveHandler;
  NDIS_TCP_OFFLOAD_SEND_COMPLETE       NdisTcpOffloadSendComplete;
  NDIS_TCP_OFFLOAD_RECEIVE_COMPLETE    NdisTcpOffloadReceiveComplete;
  NDIS_TCP_OFFLOAD_DISCONNECT_COMPLETE NdisTcpOffloadDisconnectComplete;
  NDIS_TCP_OFFLOAD_FORWARD_COMPLETE    NdisTcpOffloadForwardComplete;
} NDIS_TCP_OFFLOAD_EVENT_HANDLERS, *PNDIS_TCP_OFFLOAD_EVENT_HANDLERS;
```

## Members


`Header`

The NDIS object header, which is formatted as an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a> structure.

`NdisTcpOffloadEventHandler`

The entry point for the 
     <a href="https://msdn.microsoft.com/b62e8a07-fe7b-4c52-8795-19e4bb889b6e">
     NdisTcpOffloadEventHandler</a> function.

`NdisTcpOffloadReceiveHandler`

The entry point for the 
     <a href="https://msdn.microsoft.com/a45dede9-6559-4207-a49f-d9627054433a">
     NdisTcpOffloadReceiveHandler</a> function.

`NdisTcpOffloadSendComplete`

The entry point for the 
     <a href="https://msdn.microsoft.com/1689b6f9-88f3-456f-9a7c-c6b4e76cb336">
     NdisTcpOffloadSendComplete</a> function.

`NdisTcpOffloadReceiveComplete`

The entry point for the 
     <a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
     NdisTcpOffloadReceiveComplete</a> function.

`NdisTcpOffloadDisconnectComplete`

The entry point for the 
     <a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
     NdisTcpOffloadDisconnectComplete</a> function.

`NdisTcpOffloadForwardComplete`

The entry point for the 
     <a href="https://msdn.microsoft.com/080949ab-8a27-4d13-992e-597210d4882c">
     NdisTcpOffloadForwardComplete</a> function.

## Remarks
An offload target copies the entry points in the NDIS_TCP_OFFLOAD_EVENT_HANDLERS structure into its
    own internal data structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff566588">NDIS_OBJECT_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563595">NdisMGetOffloadHandlers</a>



<a href="https://msdn.microsoft.com/e862d9fe-a60c-4397-95ce-62aa1ef17eae">
   NdisTcpOffloadDisconnectComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564595">NdisTcpOffloadEventHandler</a>



<a href="https://msdn.microsoft.com/d5b1341b-cbe0-483c-9abb-b8706f2db2dd">
   NdisTcpOffloadReceiveComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564606">NdisTcpOffloadReceiveHandler</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564609">NdisTcpOffloadSendComplete</a>