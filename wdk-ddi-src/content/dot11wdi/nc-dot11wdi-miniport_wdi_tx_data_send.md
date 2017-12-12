---
UID: NC.dot11wdi.MINIPORT_WDI_TX_DATA_SEND
title: MINIPORT_WDI_TX_DATA_SEND
author: windows-driver-content
description: The MiniportWdiTxDataSend handler function specifies an RA-TID or port queue to transmit from. It is issued in the context of the TX thread from the operating system, resume indication, or a work item.
old-location: netvista\miniportwditxdatasend.htm
old-project: netvista
ms.assetid: A9EB1E8C-BD10-450F-9F4B-CD19C8AF13EA
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: _SYNTH_STATS, *PSYNTH_STATS, SYNTH_STATS
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
req.alt-api: MiniportWdiTxDataSend
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

# MINIPORT_WDI_TX_DATA_SEND callback



## -description
The 
  MiniportWdiTxDataSend handler function specifies an RA-TID or port queue to transmit from. It is issued in the context of the TX thread from the operating system, resume indication, or a work item.

This is a WDI miniport handler inside <a href="netvista.ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.



## -prototype

````
MINIPORT_WDI_TX_DATA_SEND MiniportWdiTxDataSend;

VOID MiniportWdiTxDataSend(
  _In_ TAL_TXRX_HANDLE  MiniportTalTxRxContext,
  _In_ WDI_PORT_ID      PortId,
  _In_ WDI_PEER_ID      PeerId,
  _In_ WDI_EXTENDED_TID ExTid,
  _In_ UINT16           NumQueueFrames,
  _In_ UINT32           NumActiveFrames,
  _In_ BOOLEAN          bRobustnessFlag
)
{ ... }
````


## -parameters

### -param MiniportTalTxRxContext [in]

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


### -param PortId [in]

The port ID.


### -param PeerId [in]

The peer ID.


### -param ExTid [in]

The Extended TID.


### -param NumQueueFrames [in]

The queue length, in frames.


### -param NumActiveFrames [in]

The total number of frames in action (schedulable) queues.


### -param bRobustnessFlag [in]

The robustness flag. If the robustness flag is set to TRUE, the NIC ensures reliable delivery within a small number of retries by aggressively lowering the TX data rate used for the frame using CTS and/or other mechanisms.


## -returns
This callback function does not return a value.


## -remarks
In port queuing mode, the <a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a> are set to wildcards.
In the context of the send request, the TxEngine issues <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_dequeue_ind.md">NdisWdiTxDequeueIndication</a> to take ownership of a number of frames from the FIFO RA-TID queue and transfer them to the target. If it cannot dequeue any frames, the TxEngine issues <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a> in the same context instead of <i>NdisWdiTxDequeueIndication</i>.

The TxEngine must issue a transfer complete and send complete indications to return ownership of any frames it dequeues to TxMgr.  If the transfer complete contains a failure code, the TxEngine must not issue a send completion.

To define a MiniportWdiTxDataSend function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiTxDataSend function that is named "MyTxDataSend", use the <b>MINIPORT_WDI_TX_DATA_SEND</b> type as shown in this code example:

Then, implement your function as follows:

The <b>MINIPORT_WDI_TX_DATA_SEND</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TX_DATA_SEND</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>. 


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
<a href="netvista.ndis_miniport_wdi_data_handlers">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_dequeue_ind.md">NdisWdiTxDequeueIndication</a>
</dt>
<dt>
<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_pause_ind.md">NdisWdiTxSendPauseIndication</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297640">WDI_EXTENDED_TID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
</dt>
<dt>
<a href="netvista.wdi_tx_path">WDI TX path</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_DATA_SEND callback function%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

