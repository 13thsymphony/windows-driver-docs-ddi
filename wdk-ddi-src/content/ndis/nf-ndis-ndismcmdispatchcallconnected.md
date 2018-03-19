---
UID: NF:ndis.NdisMCmDispatchCallConnected
title: NdisMCmDispatchCallConnected macro
author: windows-driver-content
description: NdisMCmDispatchCallConnected notifies NDIS and the client that data transfers can begin on a VC that the MCM driver created for an incoming call initiated on a remote node.
old-location: netvista\ndismcmdispatchcallconnected.htm
old-project: netvista
ms.assetid: b47976ad-fdde-48cb-bb30-4eaf25489143
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMCmDispatchCallConnected, NdisMCmDispatchCallConnected macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_3d3199be-36e5-445e-986d-984a4f778da0.xml, ndis/NdisMCmDispatchCallConnected, netvista.ndismcmdispatchcallconnected
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDispatchCallConnected   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDispatchCallConnected   (NDIS 5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
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
-	ndis.h
api_name:
-	NdisMCmDispatchCallConnected
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMCmDispatchCallConnected function
<b>NdisMCmDispatchCallConnected</b> notifies NDIS and the client that data transfers can begin on a VC that
  the MCM driver created for an 
  <i>incoming</i> call initiated on a remote node.

## Syntax

````
VOID NdisMCmDispatchCallConnected(
  [in] NDIS_HANDLE NdisVcHandle
);
````

## Parameters

`_H_`

TBD


## Return Value

None

## Remarks

An MCM driver's 
    <a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
    ProtocolCmIncomingCallComplete</a> function calls 
    <b>NdisMCmDispatchCallConnected</b> to complete the final handshake for an incoming call from a remote
    node, which the local client has already accepted.

A call to 
    <b>NdisMCmDispatchCallConnected</b> causes NDIS to call the client's 
    <a href="..\ndis\nc-ndis-protocol_cl_call_connected.md">
    ProtocolClCallConnected</a> function.

Only connection-oriented miniport drivers that provide integrated call-management support can call 
    <b>NdisMCmDispatchCallConnected</b>. Stand-alone call managers, which register themselves with NDIS as
    protocol drivers, call 
    <b>NdisCmDispatchCallConnected</b> instead.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMCmDispatchCallConnected   (NDIS 5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMCmDispatchCallConnected   (NDIS 5.1)) in Windows XP.  |
| **Target Platform** | Desktop |
| **Header** | ndis.h (include Ndis.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_MCM_Function |

## See Also

<a href="..\ndis\nc-ndis-protocol_cm_incoming_call_complete.md">
   ProtocolCmIncomingCallComplete</a>



<a href="..\ndis\nf-ndis-ndismcmdispatchincomingcall.md">NdisMCmDispatchIncomingCall</a>



<a href="..\ndis\nf-ndis-ndismcmcreatevc.md">NdisMCmCreateVc</a>



<a href="..\ndis\nf-ndis-ndiscmdispatchcallconnected.md">NdisCmDispatchCallConnected</a>



<a href="..\ndis\nc-ndis-protocol_cl_call_connected.md">ProtocolClCallConnected</a>