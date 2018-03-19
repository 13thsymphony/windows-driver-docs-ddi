---
UID: NS:ndischimney._NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: "_NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's generic chimney offload entry points.
old-location: netvista\ndis_client_chimney_offload_generic_characteristics.htm
old-project: netvista
ms.assetid: 66eb9528-e026-44cd-a775-c8d963036adc
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, netvista.ndis_client_chimney_offload_generic_characteristics, tcp_chim_struct_5db55d5e-f540-4f60-9f3b-adcd24932b1d.xml"
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
-	NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
---

# _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies a protocol driver's
  generic chimney offload entry points. Generic chimney offload entry points apply to all chimney offload
  types. Currently, TCP chimney offload is the only defined chimney offload type.

## Syntax
````
typedef struct _NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                  Header;
  ULONG                               Flags;
  INITIATE_OFFLOAD_COMPLETE_HANDLER   InitiateOffloadCompleteHandler;
  TERMINATE_OFFLOAD_COMPLETE_HANDLER  TerminateOffloadCompleteHandler;
  UPDATE_OFFLOAD_COMPLETE_HANDLER     UpdateOffloadCompleteHandler;
  INVALIDATE_OFFLOAD_COMPLETE_HANDLER InvalidateOffloadCompleteHandler;
  QUERY_OFFLOAD_COMPLETE_HANDLER      QueryOffloadCompleteHandler;
  INDICATE_OFFLOAD_EVENT_HANDLER      IndicateOffloadEventHandler;
} NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS;
````

## Members


`Header`

The header of the NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.

`Flags`

Reserved for system use.

`InitiateOffloadCompleteHandler`

Specifies the entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-initiate_offload_complete_handler.md">
     ProtocolInitiateOffloadComplete</a> function.

`TerminateOffloadCompleteHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-terminate_offload_complete_handler.md">
     ProtocolTerminateOffloadComplete</a> function.

`UpdateOffloadCompleteHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-update_offload_complete_handler.md">
     ProtocolUpdateOffloadComplete</a> function.

`InvalidateOffloadCompleteHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-invalidate_offload_complete_handler.md">
     ProtocolInvalidateOffloadComplete</a> function.

`QueryOffloadCompleteHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-query_offload_complete_handler.md">
     ProtocolQueryOffloadComplete</a> function.

`IndicateOffloadEventHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-indicate_offload_event_handler.md">
     ProtocolIndicateOffloadEvent</a> function.

## Remarks
To register its generic chimney offload entry points, a protocol or intermediate driver calls the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function,
    the protocol or intermediate driver passes a pointer to the
    NDIS_CLIENT_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="..\ndischimney\nc-ndischimney-initiate_offload_complete_handler.md">
   ProtocolInitiateOffloadComplete</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\nc-ndischimney-terminate_offload_complete_handler.md">
   ProtocolTerminateOffloadComplete</a>



<a href="..\ndischimney\nc-ndischimney-query_offload_complete_handler.md">
   ProtocolQueryOffloadComplete</a>



<a href="..\ndischimney\nc-ndischimney-invalidate_offload_complete_handler.md">
   ProtocolInvalidateOffloadComplete</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndischimney\nc-ndischimney-update_offload_complete_handler.md">
   ProtocolUpdateOffloadComplete</a>



<a href="..\ndis\nc-ndis-set_options.md">ProtocolSetOptions</a>



<a href="..\ndischimney\nc-ndischimney-indicate_offload_event_handler.md">
   ProtocolIndicateOffloadEvent</a>