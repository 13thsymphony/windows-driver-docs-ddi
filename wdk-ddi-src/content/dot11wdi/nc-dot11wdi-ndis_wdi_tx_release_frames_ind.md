---
UID: NC.dot11wdi.NDIS_WDI_TX_RELEASE_FRAMES_IND
title: NDIS_WDI_TX_RELEASE_FRAMES_IND
author: windows-driver-content
description: The NdisWdiTxReleaseFrameIndication callback function releases up to a specified number or aggregate cost of frames queued to a given peer-TID combination when transmission is paused.
old-location: netvista\ndiswditxreleaseframesindication.htm
old-project: NetVista
ms.assetid: 1324D516-8AEF-4357-86EC-81F6EBDC8FB9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: _SYNTH_STATS, *PSYNTH_STATS, SYNTH_STATS, PSYNTH_STATS
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
req.alt-api: NdisWdiTxReleaseFrameIndication
req.alt-loc: dot11wdi.h
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
---

# NDIS_WDI_TX_RELEASE_FRAMES_IND callback



## -description
The NdisWdiTxReleaseFrameIndication callback function releases up to a specified number or aggregate cost of frames queued to a given peer-TID combination when transmission is paused.  If the specified queues are not paused, none of the NET_BUFFER_LISTs are released.

This is a callback inside <a href="netvista.ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.



## -prototype

````
NDIS_WDI_TX_RELEASE_FRAMES_IND NdisWdiTxReleaseFrameIndication;

VOID NdisWdiTxReleaseFrameIndication(
  _In_  NDIS_HANDLE      NdisMiniportDataPathHandle,
  _In_  WDI_PORT_ID      PortId,
  _In_  WDI_PEER_ID      PeerId,
  _In_  UINT32           ExTidBitmask,
  _In_  UINT8            MaxNumFrames,
  _In_  UINT16           Credit,
  _Out_ PNET_BUFFER_LIST *ppNBL
)
{ ... }
````


## -parameters

### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID. Must be a non-wildcard value.


### -param PeerId [in]

The peer ID. Must be a non-wildcard value.


### -param ExTidBitmask [in]

The Extended TID bitmask.


### -param MaxNumFrames [in]

Maximum frame count. <i>MaxNumFrames</i> is ignored if it is set to <b>WDI_TX_MAX_FRAME_COUNT_INVALID</b> (0xFF).


### -param Credit [in]

Credit. <i>Credit</i> is ignored if it is set to <b>WDI_TX_CREDIT_INVALID</b> (0xFFFF).


### -param ppNBL [out]

Pointer to a pointer to a <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> chain of released frames.


## -returns
This callback function does not return a value.


## -remarks
if one of the specified queues is paused with <b>WDI_TX_PAUSE_REASON_PS</b>, the TAL/Target does not issue this indication until it has received a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a> indication for that queue.

This indication is only allowed when <b>TargetPriorityQueueing</b> is false.

The TxMgr may return a list of <a href="netvista.net_buffer_list">NET_BUFFER_LIST</a> that exceed the limit of the number of frames or frame cost. This only happens if the frames are being requeued after being send completed with status of Postponed and with identical sequence number, which indicates they were originally transmitted as part of a single A-MSDU.


## -requirements
<table>
<tr>
<th width="30%">
Minimum supported client

</th>
<td width="70%">
Windows 10

</td>
</tr>
<tr>
<th width="30%">
Minimum supported server

</th>
<td width="70%">
Windows Server 2016

</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Dot11wdi.h</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="netvista.ndis_wdi_data_api">NDIS_WDI_DATA_API</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_tal_queue_in_order.md">MiniportWdiTxTalQueueInOrder</a>
</dt>
<dt>
<a href="netvista.net_buffer_list">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
</dt>
<dt>
<a href="netvista.wdi_tx_pause_reason">WDI_TX_PAUSE_REASON</a>
</dt>
<dt>
<a href="netvista.wdi_txrx_capabilities">WDI_TXRX_CAPABILITIES</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [NetVista\netvista]:%20NDIS_WDI_TX_RELEASE_FRAMES_IND callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

