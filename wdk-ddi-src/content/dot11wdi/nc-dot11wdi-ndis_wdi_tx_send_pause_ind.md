---
UID: NC:dot11wdi.NDIS_WDI_TX_SEND_PAUSE_IND
title: NDIS_WDI_TX_SEND_PAUSE_IND
author: windows-driver-content
description: The NdisWdiTxSendPauseIndication callback function pauses transmissions on a given port to a given peer or peer-TID combination.
old-location: netvista\ndiswditxsendpauseindication.htm
old-project: netvista
ms.assetid: A8001D08-36B8-4557-A763-103BDC807CA4
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_WDI_TX_SEND_PAUSE_IND, NdisWdiTxSendPauseIndication, NdisWdiTxSendPauseIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxSendPauseIndication, netvista.ndiswditxsendpauseindication
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
-	UserDefined
api_location:
-	dot11wdi.h
api_name:
-	NdisWdiTxSendPauseIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# NDIS_WDI_TX_SEND_PAUSE_IND callback function
The NdisWdiTxSendPauseIndication callback function pauses transmissions on a given port to a given peer or peer-TID combination.

This is a callback inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>.

## Syntax

```
NDIS_WDI_TX_SEND_PAUSE_IND NdisWdiTxSendPauseInd;

void NdisWdiTxSendPauseInd(
  NDIS_HANDLE NdisMiniportDataPathHandle,
  WDI_PORT_ID PortId,
  WDI_PEER_ID PeerId,
  UINT32 ExTidBitmask,
  WDI_TX_PAUSE_REASON TxPauseReason
)
{...}
```

## Parameters

`NdisMiniportDataPathHandle`

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.

`PortId`

The port ID. Wildcards are accepted.

`PeerId`

The peer ID. Wildcards are accepted.

`ExTidBitmask`

The Extended TID bitmask. See <i>Remarks</i> section for more information.

`TxPauseReason`

TX pause reason bitmask, specified as <a href="https://msdn.microsoft.com/library/windows/hardware/dn898196">WDI_TX_PAUSE_REASON</a> value(s). See <i>Remarks</i> section for more information.


## Return Value

This callback function does not return a value.

## Remarks

In the <i>ExTidBitmask</i> parameter, the <i>i</i><sup>th</sup> bit represents extended TID <i>i </i>(the least significant bit is bit 0) .

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn898196">WDI_TX_PAUSE_REASON</a> bitmask may contain a set of pause reasons. The pauses reasons are cumulative, so an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_CREDIT</b> followed by an <i>NdisWdiTxSendPauseIndication</i> with a pause reason of <b>WDI_TX_PAUSE_REASON_IHV1</b> requires an <a href="https://msdn.microsoft.com/40976CC1-89A4-420F-867F-99F857670DAE">NdisWdiTxSendRestartIndication</a> with a pause reason of (<b>WDI_TX_PAUSE_REASON_CREDIT</b> | <b>WDI_TX_PAUSE_REASON_IHV1</b>) for the set of queues to be unpaused.

If the pause reason is <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/target does not issue an <a href="https://msdn.microsoft.com/40976CC1-89A4-420F-867F-99F857670DAE">NdisWdiTxSendRestartIndication</a> to any of the affected queues until it has received an <a href="https://msdn.microsoft.com/E82E19EA-4336-49DE-9CE4-DFBA0A347DFE">MiniportWdiTxTalQueueInOrder</a> notification for that queue

If <b>TargetPriorityQueueing</b> is true, <a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a> must be a wildcard.  Only port or adapter pauses are allowed in this mode.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/E82E19EA-4336-49DE-9CE4-DFBA0A347DFE">MiniportWdiTxTalQueueInOrder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297620">NDIS_WDI_DATA_API</a>



<a href="https://msdn.microsoft.com/40976CC1-89A4-420F-867F-99F857670DAE">NdisWdiTxSendRestartIndication</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898187">WDI_TXRX_CAPABILITIES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn898196">WDI_TX_PAUSE_REASON</a>