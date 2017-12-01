---
UID: NC.dot11wdi.NDIS_WDI_PEER_CREATE_IND
title: NDIS_WDI_PEER_CREATE_IND
author: windows-driver-content
description: The NdisWdiPeerCreateIndication callback function specifies a peer ID to associate with a peer MAC address.
old-location: netvista\ndiswdipeercreateindication.htm
old-project: netvista
ms.assetid: 58B60160-FE04-4EDE-900F-244D0F76E50D
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: SYNTHVOICEPRIORITY_INSTANCE, SYNTHVOICEPRIORITY_INSTANCE, *PSYNTHVOICEPRIORITY_INSTANCE
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
req.alt-api: NdisWdiPeerCreateIndication
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
req.iface: ISynthSinkDMus
---

# NDIS_WDI_PEER_CREATE_IND callback



## -description
<p>The NdisWdiPeerCreateIndication callback function specifies a peer ID to associate with a peer MAC address.</p>
<p>This is a callback inside <a href="..\dot11wdi\ns-dot11wdi--ndis-wdi-data-api.md">NDIS_WDI_DATA_API</a>.</p>


## -prototype

````
NDIS_WDI_PEER_CREATE_IND NdisWdiPeerCreateIndication;

VOID NdisWdiPeerCreateIndication(
  _In_ NDIS_HANDLE     NdisMiniportDataPathHandle,
  _In_ WDI_PORT_ID     PortId,
  _In_ WDI_PEER_ID     PeerId,
  _In_ WDI_MAC_ADDRESS PeerAddr
)
{ ... }
````


## -parameters
<dl>

### -param <i>NdisMiniportDataPathHandle</i> [in]

<dd>
<p>The NdisMiniportDataPathHandle passed to IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport-wdi-tal-txrx-initialize.md">MiniportWdiTalTxRxInitialize</a>.</p>
</dd>

### -param <i>PortId</i> [in]

<dd>
<p>The port ID.</p>
</dd>

### -param <i>PeerId</i> [in]

<dd>
<p>The peer ID. This is used to identify the  peer in subsequent commands and indications.</p>
</dd>

### -param <i>PeerAddr</i> [in]

<dd>
<p>The peer MAC address.</p>
</dd>
</dl>

## -returns
<p>This callback function does not return a value.</p>

## -remarks
<p>This must be received and processed prior to exchanging frames with the peer.</p>

<p>A port operating in AP or Wi-Fi Direct GO mode may simultaneously have more than one peer (clients).  When a port is operating in AP or Wi-Fi Direct GO mode, the IHV miniport creates a 'peer' for group addressed traffic (by passing a broadcast MAC address).  All multicast and broadcast traffic for this port is associated with this peer. In port queuing mode, the creation of the group peer by the IHV miniport is not required as Tx frame classification does not occur in this mode.</p>

<p>A port operating in any mode may create a group peer.</p>

<p>To facilitate TDLS implementation in the IHV component, a port operating in STA or Wi-Fi Direct client mode may simultaneously have more than one peer.  If  a TX frame's destination MAC address matches is associated with a non-AP/GO peer ID, the TxMgr queues the frame with a TID queue associated with that non-AP/GO peer (if WDI is operating in PeerTID queuing mode).</p>

<p>In peer queuing mode, a peer is created with all TIDs paused with <b>WDI_TX_PAUSE_REASON_PEER_CREATE</b>.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Minimum supported client</p>
</th>
<td width="70%">
<p>Windows 10</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Minimum supported server</p>
</th>
<td width="70%">
<p>Windows Server 2016</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
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
<a href="..\dot11wdi\ns-dot11wdi--ndis-wdi-data-api.md">NDIS_WDI_DATA_API</a>
</dt>
<dt>
<a href="..\dot11wdi\ns-dot11wdi--wdi-mac-address.md">WDI_MAC_ADDRESS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>
</dt>
<dt>
<a href="NULL">WDI general datapath interfaces</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_PEER_CREATE_IND callback function%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
