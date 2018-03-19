---
UID: NF:ndis.NdisCmDispatchIncomingCloseCall
title: NdisCmDispatchIncomingCloseCall function
author: windows-driver-content
description: NdisCmDispatchIncomingCloseCall tells a client to tear down an active or offered call, usually because the call manager has received a request from the network to close the connection.
old-location: netvista\ndiscmdispatchincomingclosecall.htm
old-project: netvista
ms.assetid: f0f1221d-3d95-4d4c-acd0-6bcd653241c4
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisCmDispatchIncomingCloseCall, NdisCmDispatchIncomingCloseCall function [Network Drivers Starting with Windows Vista], condis_call_manager_ref_877248ee-cc60-430c-836c-d2580627363f.xml, ndis/NdisCmDispatchIncomingCloseCall, netvista.ndiscmdispatchincomingclosecall
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows XP.
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
-	NdisCmDispatchIncomingCloseCall
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisCmDispatchIncomingCloseCall function
<b>NdisCmDispatchIncomingCloseCall</b> tells a client to tear down an active or offered call, usually
  because the call manager has received a request from the network to close the connection.

## Syntax

````
VOID NdisCmDispatchIncomingCloseCall(
  _In_     NDIS_STATUS CloseStatus,
  _In_     NDIS_HANDLE NdisVcHandle,
  _In_opt_ PVOID       Buffer,
  _In_     UINT        Size
);
````

## Parameters

`CloseStatus`

Specifies a CM-determined NDIS_STATUS_<i>XXX</i>, indicating the reason for the disconnect request. During normal network operations, a call
     manager passes NDIS_STATUS_SUCCESS to indicate that it has received a request, initiated by the remote
     party, to close an active call.

`NdisVcHandle`

Specifies the handle to the VC of the call being disconnected. This handle was supplied by NDIS
     when the VC was originally created, whether by the call manager or client, with 
     <a href="..\ndis\nf-ndis-ndiscocreatevc.md">NdisCoCreateVc</a>.

`Buffer`

Pointer to a caller-allocated resident buffer containing additional protocol-specific disconnect
     data, if any. Depending on the underlying medium, this pointer can be <b>NULL</b>

`Size`

Specifies the size in bytes of the buffer, zero if 
     <i>Buffer</i> is <b>NULL</b>.


## Return Value

None

## Remarks

In the course of normal network operations, a stand-alone CM calls 
    <b>NdisCmDispatchIncomingCloseCall</b> with the 
    <i>CloseStatus</i> set to NDIS_STATUS_SUCCESS because the corresponding client on the remote node has
    called 
    <a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>.

However, a call manager also can call 
    <b>NdisCmDispatchIncomingCloseCall</b> if either of the following occurs:

<ul>
<li>
The call manager has notified a client of an incoming call offer. When the CM's 
      <a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
      ProtocolCmIncomingCallComplete</a> function is called with the client's acceptance, it validates the
      input call parameters, which that client has modified. 
      <i>ProtocolCmIncomingCallComplete</i> determines that the client is proposing unsupportable call
      parameters for the connection, so it calls 
      <b>NdisCmDispatchIncomingCloseCall</b>.

</li>
<li>
Abormal network conditions force the call manager to tear down active calls. For example, if the
      call manager is notified when any link on the connection between this client and the remote party to
      the connection goes down, the CM would call 
      <b>NdisCmDispatchIncomingCloseCall</b> to prevent the client from attempting (or expecting) further data
      transfers on such a broken connection.

</li>
</ul>
After tearing down any call, the original creator of the VC is responsible for calling 
    <a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a> after releasing any
    additional resources it had associated with the VC.

A call to 
    <b>NdisCmDispatchIncomingCloseCall</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">
    ProtocolClIncomingCloseCall</a> function.

Only stand-alone call managers, which register themselves with NDIS as protocol drivers, can call 
    <b>NdisCmDispatchIncomingCloseCall</b>. Connection-oriented miniport drivers that provide call-management
    support call 
    <a href="..\ndis\nf-ndis-ndismcmdispatchincomingcall.md">
    NdisMCmDispatchIncomingCall</a> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see       NdisCmDispatchIncomingCloseCall (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_CallManager_Function |

## See Also

<a href="..\ndis\nf-ndis-ndiscmdispatchincomingdropparty.md">
   NdisCmDispatchIncomingDropParty</a>



<a href="..\ndis\nf-ndis-ndiscodeletevc.md">NdisCoDeleteVc</a>



<a href="..\ndis\nf-ndis-ndisclclosecall.md">NdisClCloseCall</a>



<a href="..\ndis\nf-ndis-ndismcmdispatchincomingclosecall.md">
   NdisMCmDispatchIncomingCloseCall</a>



<a href="..\ndis\nc-ndis-protocol_cl_incoming_close_call.md">ProtocolClIncomingCloseCall</a>



<a href="..\ndis\nc-ndis-protocol_co_receive_net_buffer_lists.md">
   ProtocolCoReceiveNetBufferLists</a>



<a href="..\ndis\nc-ndis-protocol_co_status_ex.md">ProtocolCoStatusEx</a>