---
UID: NF:ndis.NdisMSendNetBufferListsComplete
title: NdisMSendNetBufferListsComplete function
author: windows-driver-content
description: Miniport drivers call the NdisMSendNetBufferListsComplete function to return a linked list of NET_BUFFER_LIST structures to an overlying driver and to return the final status of a send request.
old-location: netvista\ndismsendnetbufferlistscomplete.htm
old-project: netvista
ms.assetid: 33890582-5eba-4cc1-a0d9-ec07f18da453
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisMSendNetBufferListsComplete, NdisMSendNetBufferListsComplete function [Network Drivers Starting with Windows Vista], ndis/NdisMSendNetBufferListsComplete, ndis_sendrcv_ref_11bdd96b-0ba8-475a-ba6e-03492e2993d7.xml, netvista.ndismsendnetbufferlistscomplete
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
req.ddi-compliance: Irql_SendRcv_Function, NdisTimedDataHang, NdisTimedDataSend
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
-	NdisMSendNetBufferListsComplete
product:
- Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMSendNetBufferListsComplete function
Miniport drivers call the 
  <b>NdisMSendNetBufferListsComplete</b> function to return a linked list of 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures to an overlying
  driver and to return the final status of a send request.

## Syntax

```
void NdisMSendNetBufferListsComplete(
  NDIS_HANDLE      MiniportAdapterHandle,
  PNET_BUFFER_LIST NetBufferList,
  ULONG            SendCompleteFlags
);
```

## Parameters

`MiniportAdapterHandle`

The miniport handle that NDIS passed to the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.

`NetBufferList`

TBD

`SendCompleteFlags`

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL flag which; if set, indicates
     that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.


## Return Value

None

## Remarks

A miniport driver calls 
    <b>NdisMSendNetBufferListsComplete</b> to complete send requests that NDIS made to the driver's 
    <a href="https://msdn.microsoft.com/0bd5966d-66a6-4548-8c84-7cedced2cf40">
    MiniportSendNetBufferLists</a> function. The miniport driver specifies a linked list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures that are
    associated with the completed send requests. While the status of the send requests is pending, the
    miniport driver retains ownership of the NET_BUFFER_LIST structures and all the protocol-allocated
    resources that are associated with the NET_BUFFER_LIST structures.

After a miniport driver calls 
    <b>NdisMSendNetBufferListsComplete</b>, NDIS calls the 
    <a href="https://msdn.microsoft.com/bc9197c5-ce0b-42b2-8225-fb9d83427ac8">
    ProtocolSendNetBufferListsComplete</a> function of the driver that called the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff564535">NdisSendNetBufferLists</a> function to
    initiate the send request.

The miniport driver can complete send requests in any order. For example, the miniport driver could
    concatenate the NET_BUFFER_LIST structure lists from multiple 
    <i>MiniportSendNetBufferLists</i> calls or split up a list from a 
    <i>MiniportSendNetBufferLists</i> call. However, the miniport driver must not modify the list of 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structures that are associated with a
    NET_BUFFER_LIST structure.

The miniport driver must set one of the following status codes in the 
    <b>Status</b> member of each NET_BUFFER_LIST structure that the 
    <i>NetBufferLists</i> parameter specifies:



A miniport driver's call to 
    <b>NdisMSendNetBufferListsComplete</b> does not necessarily mean that the data for a send request has been
    transmitted over the network. The data might be queued in the NIC hardware.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported in NDIS 6.0 and later.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_SendRcv_Function, NdisTimedDataHang, NdisTimedDataSend |

## See Also

<a href="https://msdn.microsoft.com/17111aa3-c02f-494a-af97-5ab34c152451">MiniportCancelSend</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/0bd5966d-66a6-4548-8c84-7cedced2cf40">MiniportSendNetBufferLists</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564535">NdisSendNetBufferLists</a>