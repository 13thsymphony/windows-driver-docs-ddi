---
UID: NC:dot11wdi.NDIS_WDI_TX_RELEASE_FRAMES_IND
title: NDIS_WDI_TX_RELEASE_FRAMES_IND
author: windows-driver-content
description: The NdisWdiTxReleaseFrameIndication callback function releases up to a specified number or aggregate cost of frames queued to a given peer-TID combination when transmission is paused.
old-location: netvista\ndiswditxreleaseframesindication.htm
old-project: netvista
ms.assetid: 1324D516-8AEF-4357-86EC-81F6EBDC8FB9
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NDIS_WDI_TX_RELEASE_FRAMES_IND, NdisWdiTxReleaseFrameIndication, NdisWdiTxReleaseFrameIndication callback function [Network Drivers Starting with Windows Vista], dot11wdi/NdisWdiTxReleaseFrameIndication, netvista.ndiswditxreleaseframesindication
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
-	NdisWdiTxReleaseFrameIndication
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# NDIS_WDI_TX_RELEASE_FRAMES_IND callback function
The NdisWdiTxReleaseFrameIndication callback function releases up to a specified number or aggregate cost of frames queued to a given peer-TID combination when transmission is paused.  If the specified queues are not paused, none of the NET_BUFFER_LISTs are released.

This is a callback inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>.

## Syntax

```
NDIS_WDI_TX_RELEASE_FRAMES_IND NdisWdiTxReleaseFramesInd;

void NdisWdiTxReleaseFramesInd(
  NDIS_HANDLE NdisMiniportDataPathHandle,
  WDI_PORT_ID PortId,
  WDI_PEER_ID PeerId,
  UINT32 ExTidBitmask,
  UINT8 MaxNumFrames,
  UINT16 Credit,
  PNET_BUFFER_LIST *ppNBL
)
{...}
```

## Parameters

`NdisMiniportDataPathHandle`

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`PortId`

The port ID. Must be a non-wildcard value.

`PeerId`

The peer ID. Must be a non-wildcard value.

`ExTidBitmask`

The Extended TID bitmask.

`MaxNumFrames`

Maximum frame count. <i>MaxNumFrames</i> is ignored if it is set to <b>WDI_TX_MAX_FRAME_COUNT_INVALID</b> (0xFF).

`Credit`

Credit. <i>Credit</i> is ignored if it is set to <b>WDI_TX_CREDIT_INVALID</b> (0xFFFF).

`*ppNBL`

Pointer to a pointer to a <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> chain of released frames.


## Return Value

This callback function does not return a value.

## Remarks

if one of the specified queues is paused with <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/Target does not issue this indication until it has received a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a> indication for that queue.

This indication is only allowed when <b>TargetPriorityQueueing</b> is false.

The TxMgr may return a list of <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> that exceed the limit of the number of frames or frame cost. This only happens if the frames are being requeued after being send completed with status of Postponed and with identical sequence number, which indicates they were originally transmitted as part of a single A-MSDU.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_wdi_data_api.md">NDIS_WDI_DATA_API</a>



<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_wdi_txrx_target_capabilities.md">WDI_TXRX_CAPABILITIES</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_tx_pause_reason.md">WDI_TX_PAUSE_REASON</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_RELEASE_FRAMES_IND callback function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>