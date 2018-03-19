---
UID: NS:ndischimney._NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
title: "_NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS"
author: windows-driver-content
description: The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney offload miniport entry points of an offload target or intermediate driver.
old-location: netvista\ndis_provider_chimney_offload_generic_characteristics.htm
old-project: netvista
ms.assetid: e80a9999-2e4e-4da0-8aae-54ee71d9249d
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, ndischimney/PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, netvista.ndis_provider_chimney_offload_generic_characteristics, tcp_chim_struct_3145314d-c0a6-4d4e-b489-c38dda6c43e5.xml"
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
-	NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS
---

# _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure
<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

The NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure specifies the generic chimney
  offload miniport entry points of an offload target or intermediate driver. Generic chimney offload entry
  points pertain to all chimney offload types. Currently, TCP chimney offload is the only defined chimney
  offload type.

## Syntax
````
typedef struct _NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS {
  NDIS_OBJECT_HEADER           Header;
  ULONG                        Flags;
  W_INITIATE_OFFLOAD_HANDLER   InitiateOffloadHandler;
  W_TERMINATE_OFFLOAD_HANDLER  TerminateOffloadHandler;
  W_UPDATE_OFFLOAD_HANDLER     UpdateOffloadHandler;
  W_INVALIDATE_OFFLOAD_HANDLER InvalidateOffloadHandler;
  W_QUERY_OFFLOAD_HANDLER      QueryOffloadHandler;
} NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS, *PNDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS;
````

## Members


`Header`

The header of the NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure. The header is
     formatted as an 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure. The
     NDIS_OBJECT_HEADER structure contains the revision number of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure and the size of the
     NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure, including the header, in bytes. The 
     <b>Type</b> member of the header is not significant.

`Flags`

Reserved for system use.

`InitiateOffloadHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">
     MiniportInitiateOffload</a> function.

`TerminateOffloadHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">
     MiniportTerminateOffload</a> function.

`UpdateOffloadHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">
     MiniportUpdateOffload</a> function.

`InvalidateOffloadHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">
     MiniportInvalidateOffload</a> function.

`QueryOffloadHandler`

The entry point of the driver's 
     <a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">
     MiniportQueryOffload</a> function.

## Remarks
To register its generic chimney offload entry points, an offload target or intermediate driver calls
    the 
    <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a> function
    in the context of the 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a> function. To the 
    <b>NdisSetOptionalHandlers</b> function, the offload target or intermediate driver passes a pointer to the
    NDIS_PROVIDER_CHIMNEY_OFFLOAD_GENERIC_CHARACTERISTICS structure.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ndischimney.h (include Ndischimney.h) |

## See Also

<a href="..\ndischimney\nc-ndischimney-w_query_offload_handler.md">MiniportQueryOffload</a>



<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndischimney\nc-ndischimney-w_update_offload_handler.md">MiniportUpdateOffload</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff570269">MiniportSetOptions</a>



<a href="..\ndischimney\nc-ndischimney-w_initiate_offload_handler.md">MiniportInitiateOffload</a>



<a href="..\ndischimney\nc-ndischimney-w_invalidate_offload_handler.md">MiniportInvalidateOffload</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndischimney\nc-ndischimney-w_terminate_offload_handler.md">MiniportTerminateOffload</a>