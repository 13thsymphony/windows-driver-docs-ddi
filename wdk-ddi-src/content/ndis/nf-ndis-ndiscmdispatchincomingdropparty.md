---
UID: NF:ndis.NdisCmDispatchIncomingDropParty
title: NdisCmDispatchIncomingDropParty function
author: windows-driver-content
description: NdisCmDispatchIncomingDropParty notifies a client that it should remove a particular party on a multipoint VC, usually because the call manager has received a request over the network to close an active multipoint connection.
old-location: netvista\ndiscmdispatchincomingdropparty.htm
old-project: netvista
ms.assetid: 9dce2b0a-1d0c-4c87-a32f-8bf72bb91cfe
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisCmDispatchIncomingDropParty, NdisCmDispatchIncomingDropParty function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_6f7730c4-030a-45a6-b873-833bf8033ce7.xml, ndis/NdisCmDispatchIncomingDropParty, netvista.ndiscmdispatchincomingdropparty
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingDropParty (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmDispatchIncomingDropParty (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_CallManager_Function
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
-	NdisCmDispatchIncomingDropParty
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisCmDispatchIncomingDropParty function
<b>NdisCmDispatchIncomingDropParty</b> notifies a client that it should remove a particular party on a
  multipoint VC, usually because the call manager has received a request over the network to close an active
  multipoint connection.

## Syntax

````
VOID NdisCmDispatchIncomingDropParty(
  _In_     NDIS_STATUS DropStatus,
  _In_     NDIS_HANDLE NdisPartyHandle,
  _In_opt_ PVOID       Buffer,
  _In_     UINT        Size
);
````

## Parameters

`DropStatus`

Indicates the reason this party is being dropped, usually NDIS_STATUS_SUCCESS if the remote party
     simply requested that its connection be closed.

`NdisPartyHandle`

Specifies the handle that identifies the party to be dropped from the multipoint VC, which must
     have other parties that are still connected.

`Buffer`

Pointer to a caller-allocated resident buffer containing additional protocol-specific data
     received from the remote party, if any. Depending on the underlying medium, this pointer can be
     <b>NULL</b>.

`Size`

Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.


## Return Value

None

## Remarks

In the course of normal network operations, a stand-alone call manager's 
    <a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">
    ProtocolCoReceiveNetBufferLists</a> function calls 
    <b>NdisCmDispatchIncomingDropParty</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because a remote client on a multipoint connection has
    called 
    <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>.

However, a call manager also can call 
    <b>NdisCmDispatchIncomingDropParty</b> with a CM-determined 
    <i>CloseStatus</i> at the behest of the network itself if abnormal network conditions occur, such as the
    failure of a switch on the path between the local client and one or more client(s) on an established
    multipoint connection.

A call to 
    <b>NdisCmDispatchIncomingDropParty</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">
    ProtocolClIncomingDropParty</a> function.

If the 
    <i>NdisPartyHandle</i> identifies the last remaining party on the given VC, the CM calls 
    <a href="..\ndis\nf-ndis-ndiscmdispatchincomingclosecall.md">
    NdisCmDispatchIncomingCloseCall</a>, rather than 
    <b>NdisCmDispatchIncomingDropParty</b>.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingDropParty</b>. Connection-oriented miniport drivers that provide integrated
    call-management support call 
    <b>NdisMCmDispatchIncomingDropParty</b> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingDropParty (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmDispatchIncomingDropParty (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_CallManager_Function |

## See Also

<a href="..\ndis\nc-ndis-protocol_cl_incoming_drop_party.md">ProtocolClIncomingDropParty</a>



<a href="..\ndis\nf-ndis-ndismcmdispatchincomingdropparty.md">
   NdisMCmDispatchIncomingDropParty</a>



<a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">
   ProtocolCoReceiveNetBufferLists</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchincomingclosecall.md">
   NdisCmDispatchIncomingCloseCall</a>



<a href="..\ndis\nf-ndis-ndiscldropparty.md">NdisClDropParty</a>