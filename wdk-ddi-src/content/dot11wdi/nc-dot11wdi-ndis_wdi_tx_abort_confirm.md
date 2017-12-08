---
UID: NC.dot11wdi.NDIS_WDI_TX_ABORT_CONFIRM
title: NDIS_WDI_TX_ABORT_CONFIRM
author: windows-driver-content
description: The NdisWdiTxAbortConfirm callback function indicates an asynchronous confirmation of a MiniportWdiTxAbort from WDI.
old-location: netvista\ndiswditxabortconfirm.htm
old-project: netvista
ms.assetid: 1619BF14-DDEE-48CB-8E31-0CC17C8A4C6A
ms.author: windowsdriverdev
ms.date: 12/6/2017
ms.keywords: _SYNTH_STATS, SYNTH_STATS, *PSYNTH_STATS
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
req.alt-api: NdisWdiTxAbortConfirm
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

# NDIS_WDI_TX_ABORT_CONFIRM callback



## -description
The NdisWdiTxAbortConfirm callback function  indicates an asynchronous confirmation of a <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tx_abort.md">MiniportWdiTxAbort</a> from WDI.
This is a callback inside <a href="netvista.ndis_wdi_data_api">NDIS_WDI_DATA_API</a>.


## -prototype

````
NDIS_WDI_TX_ABORT_CONFIRM NdisWdiTxAbortConfirm;

VOID NdisWdiTxAbortConfirm(
  _In_ NDIS_HANDLE NdisMiniportDataPathHandle
)
{ ... }
````


## -parameters

### -param NdisMiniportDataPathHandle [in]

The NdisMiniportDataPathHandle passed to the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

## -returns
This callback function does not return a value.

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
<a href="netvista.ndis_wdi_data_api">NDIS_WDI_DATA_API</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_WDI_TX_ABORT_CONFIRM callback function%20 RELEASE:%20(12/6/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
