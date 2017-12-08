---
UID: NS.DOT11WDI._WDI_TX_METADATA
title: _WDI_TX_METADATA
author: windows-driver-content
description: The WDI_TX_METADATA structure defines the TX metadata.
old-location: netvista\wdi_tx_metadata.htm
old-project: netvista
ms.assetid: 21833980-0098-43c2-822c-9d8292f7120a
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _WDI_TX_METADATA, *PWDI_TX_METADATA, WDI_TX_METADATA
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dot11wdi.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: WDI_TX_METADATA
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
req.irql: PASSIVE_LEVEL
---

# _WDI_TX_METADATA structure



## -description
The 
  WDI_TX_METADATA structure defines the TX metadata.


## -syntax

````
typedef struct _WDI_TX_METADATA {
  WDI_PORT_ID               PortID;
  WDI_PEER_ID               PeerID;
  WDI_EXTENDED_TID          ExTID;
  BOOLEAN                   IsUnicast;
  BOOLEAN                   bAllowLegacyRates;
  UINT16                    Ethertype;
  BOOLEAN                   bTxCompleteRequired;
  UINT8                     PnLength;
  UINT16                    TxCost;
  WDI_EXEMPTION_ACTION_TYPE ExemptionAction;
  WDI_TXRX_MPDU_PN          MpduPn;
  UINT64                    ReplayIHVReserved0;
  UINT64                    ReplayIHVReserved1;
  UINT16                    SeqCtl;
  UINT16                    wPad;
} WDI_TX_METADATA, *PWDI_TX_METADATA;
````


## -struct-fields

### -field PortID

Port ID of the frame.

### -field PeerID

Peer ID of the frame (only if <b>TargetPriorityQueueing</b> is false).

### -field ExTID

Extended TID of the frame (only if <b>TargetPriorityQueueing</b> is false).

### -field IsUnicast

Specifies if the frame is for a unicast recipient address.

### -field bAllowLegacyRates

Specifies if legacy rates should be used for transmitting the frame.

### -field Ethertype

Specifies the Ethertype of the frame.

### -field bTxCompleteRequired

Specifies if an <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a> is required for this frame.

### -field PnLength

Specifies the PnLength for the frame. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field TxCost

Specifies the number of credits required to dequeue the frame.

### -field ExemptionAction

Specifies the <a href="netvista.wdi_exemption_action_type">WDI_EXEMPTION_ACTION_TYPE</a> value for this frame.

### -field MpduPn

Specifies the MpduPn for the frame. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field ReplayIHVReserved0

Reserved for use by the IHV miniport for Requeued/Replayed TX frames. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.  

### -field ReplayIHVReserved1

Reserved for use by the IHV miniport for Requeued/Replayed TX frames. This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.  

### -field SeqCtl

Specifies the SeqCtl (if necessary). This is only applicable to Requeued/Replayed TX frames.  Otherwise, set to zero.

### -field wPad

Reserved.

## -remarks


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
<a href="netvista.wdi_exemption_action_type">WDI_EXEMPTION_ACTION_TYPE</a>
</dt>
<dt>
<a href="netvista.wdi_txrx_capabilities">WDI_TXRX_CAPABILITIES</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20WDI_TX_METADATA structure%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
