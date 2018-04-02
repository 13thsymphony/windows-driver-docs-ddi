---
UID: NF:ndis.NdisReturnNetBufferLists
title: NdisReturnNetBufferLists function
author: windows-driver-content
description: NDIS drivers call the NdisReturnNetBufferLists function to release ownership of a list of NET_BUFFER_LIST structures, along with the associated NET_BUFFER structures and network data.
old-location: netvista\ndisreturnnetbufferlists.htm
old-project: netvista
ms.assetid: 1a45bc5c-cdc1-46d2-905b-3d5eea3645c1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisReturnNetBufferLists, NdisReturnNetBufferLists function [Network Drivers Starting with Windows Vista], ndis/NdisReturnNetBufferLists, ndis_sendrcv_ref_9c5a4908-356f-4e7c-9351-4fec4358180d.xml, netvista.ndisreturnnetbufferlists
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_SendRcv_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisReturnNetBufferLists
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisReturnNetBufferLists function
NDIS drivers call the 
  <b>NdisReturnNetBufferLists</b> function to release ownership of a list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures, along with the
  associated 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures and network data.

## Syntax

```
void NdisReturnNetBufferLists(
  NDIS_HANDLE      NdisBindingHandle,
  PNET_BUFFER_LIST NetBufferLists,
  ULONG            ReturnFlags
);
```

## Parameters

`NdisBindingHandle`

A handle that identifies the target adapter. This handle was returned by a previous call to the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a> function. All of the 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are
     specified in this call must be from the binding that this handle identifies.

`NetBufferLists`

A pointer to a linked list of NET_BUFFER_LIST structures that are to be returned to the underlying
     driver. The linked list can contain NET_BUFFER_LIST structures from multiple previous calls to the 
     <a href="https://msdn.microsoft.com/c964b4b8-ab07-4a07-9965-5cc06c028c20">
     ProtocolReceiveNetBufferLists</a> function.

`ReturnFlags`

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_RETURN_FLAGS_DISPATCH_LEVEL flag which; if set, indicates that the
     current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.


## Return Value

None

## Remarks

If the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>ReceiveFlags</i> parameter that NDIS passed to the 
    <a href="https://msdn.microsoft.com/c964b4b8-ab07-4a07-9965-5cc06c028c20">
    ProtocolReceiveNetBufferLists</a> function was not set, the protocol driver must call 
    <b>NdisReturnNetBufferLists</b> to return the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures and associated
    data. After the protocol driver calls 
    <b>NdisReturnNetBufferLists</b>, NDIS calls the underlying miniport driver's 
    <a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
    MiniportReturnNetBufferLists</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_SendRcv_Function |

## See Also

<a href="https://msdn.microsoft.com/0f33ae87-164e-40dc-a915-28211a0d74b7">
   MiniportReturnNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/c964b4b8-ab07-4a07-9965-5cc06c028c20">
   ProtocolReceiveNetBufferLists</a>