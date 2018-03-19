---
UID: NS:ndis._NDIS_FILTER_PARTIAL_CHARACTERISTICS
title: "_NDIS_FILTER_PARTIAL_CHARACTERISTICS"
author: windows-driver-content
description: To specify optional entry points for a filter module, a filter driver initializes an NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the NdisSetOptionalHandlers function.
old-location: netvista\ndis_filter_partial_characteristics.htm
old-project: netvista
ms.assetid: 4a7f365c-a252-4d8e-bddf-684b3298db5c
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS, NDIS_FILTER_PARTIAL_CHARACTERISTICS structure [Network Drivers Starting with Windows Vista], PNDIS_FILTER_PARTIAL_CHARACTERISTICS, PNDIS_FILTER_PARTIAL_CHARACTERISTICS structure pointer [Network Drivers Starting with Windows Vista], _NDIS_FILTER_PARTIAL_CHARACTERISTICS, filter_structures_ref_34b4c497-9a4c-4d15-9d25-672a7580456b.xml, ndis/NDIS_FILTER_PARTIAL_CHARACTERISTICS, ndis/PNDIS_FILTER_PARTIAL_CHARACTERISTICS, netvista.ndis_filter_partial_characteristics"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NDIS_FILTER_PARTIAL_CHARACTERISTICS
product: Windows
targetos: Windows
req.typenames: NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS
---

# _NDIS_FILTER_PARTIAL_CHARACTERISTICS structure
To specify optional entry points for a filter module, a filter driver initializes an
  NDIS_FILTER_PARTIAL_CHARACTERISTICS structure and passes it to the 
  <a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">
  NdisSetOptionalHandlers</a> function.

## Syntax
````
typedef struct _NDIS_FILTER_PARTIAL_CHARACTERISTICS {
  NDIS_OBJECT_HEADER                            Header;
  ULONG                                         Flags;
  FILTER_SEND_NET_BUFFER_LISTS_HANDLER          SendNetBufferListsHandler;
  FILTER_SEND_NET_BUFFER_LISTS_COMPLETE_HANDLER SendNetBufferListsCompleteHandler;
  FILTER_CANCEL_SEND_HANDLER                    CancelSendNetBufferListsHandler;
  FILTER_RECEIVE_NET_BUFFER_LISTS_HANDLER       ReceiveNetBufferListsHandler;
  FILTER_RETURN_NET_BUFFER_LISTS_HANDLER        ReturnNetBufferListsHandler;
} NDIS_FILTER_PARTIAL_CHARACTERISTICS, *PNDIS_FILTER_PARTIAL_CHARACTERISTICS;
````

## Members


`Header`

The 
     <a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a> structure for the
     filter driver partial characteristics structure (NDIS_FILTER_PARTIAL_CHARACTERISTICS). Set the 
     <b>Type</b> member of the structure that 
     <b>Header</b> specifies to NDIS_OBJECT_TYPE_FILTER_PARTIAL_CHARACTERISTICS, the 
     <b>Revision</b> member to NDIS_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1, and the 
     <b>Size</b> member to NDIS_SIZEOF_FILTER_PARTIAL_CHARACTERISTICS_REVISION_1.

`Flags`

Reserved for NDIS.

`SendNetBufferListsHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">
     FilterSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

`SendNetBufferListsCompleteHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
     FilterSendNetBufferListsComplete</a> function. To bypass this function, set this member to
     <b>NULL</b>.

`CancelSendNetBufferListsHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_cancel_send_net_buffer_lists.md">
     FilterCancelSendNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

`ReceiveNetBufferListsHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">
     FilterReceiveNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

`ReturnNetBufferListsHandler`

The entry point of the caller's 
     <a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">
     FilterReturnNetBufferLists</a> function. To bypass this function, set this member to <b>NULL</b>.

## Remarks
This structure specifies optional 
    <i>FilterXxx</i> functions and other characteristics for a filter module. These characteristics override
    the default values that the driver set in the 
    <a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
    NDIS_FILTER_DRIVER_CHARACTERISTICS</a> structure that the driver passed to the 
    <a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">
    NdisFRegisterFilterDriver</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later. Supported in NDIS 6.0 and later. |
| **Header** | ndis.h (include Ndis.h) |

## See Also

<a href="..\ntddndis\ns-ntddndis-_ndis_object_header.md">NDIS_OBJECT_HEADER</a>



<a href="..\ndis\ns-ndis-_ndis_filter_driver_characteristics.md">
   NDIS_FILTER_DRIVER_CHARACTERISTICS</a>



<a href="..\ndis\nc-ndis-filter_return_net_buffer_lists.md">FilterReturnNetBufferLists</a>



<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists.md">FilterSendNetBufferLists</a>



<a href="..\ndis\nf-ndis-ndissetoptionalhandlers.md">NdisSetOptionalHandlers</a>



<a href="..\ndis\nc-ndis-filter_send_net_buffer_lists_complete.md">
   FilterSendNetBufferListsComplete</a>



<a href="..\ndis\nc-ndis-filter_cancel_send_net_buffer_lists.md">
   FilterCancelSendNetBufferLists</a>



<a href="..\ndis\nf-ndis-ndisfregisterfilterdriver.md">NdisFRegisterFilterDriver</a>



<a href="..\ndis\nc-ndis-filter_receive_net_buffer_lists.md">FilterReceiveNetBufferLists</a>