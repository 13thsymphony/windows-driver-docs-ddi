---
UID: NC:dot11wdi.MINIPORT_WDI_RX_PPDU_RSSI
title: MINIPORT_WDI_RX_PPDU_RSSI
author: windows-driver-content
description: The MiniportWdiRxPpduRssi handler function returns the absolute value of RSSI (in dB) for the PPDU. The RxMgr may request the RSSI only once per data indication using the PNET_BUFFER_LIST obtained from MiniportWdiRxGetMpdus.
old-location: netvista\miniportwdirxppdurssi.htm
old-project: netvista
ms.assetid: 34C34C42-E5E1-44F6-AC81-ADC77206DED0
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdirxppdurssi, MiniportWdiRxPpduRssi callback function [Network Drivers Starting with Windows Vista], MiniportWdiRxPpduRssi, MINIPORT_WDI_RX_PPDU_RSSI, MINIPORT_WDI_RX_PPDU_RSSI, dot11wdi/MiniportWdiRxPpduRssi
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	dot11wdi.h
apiname:
-	MiniportWdiRxPpduRssi
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_RX_PPDU_RSSI callback function
The 
  MiniportWdiRxPpduRssi handler function returns the absolute value of RSSI (in dB) for the PPDU. The RxMgr may request the RSSI only once per data indication using the PNET_BUFFER_LIST obtained from <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_rx_get_mpdus.md">MiniportWdiRxGetMpdus</a>.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_PPDU_RSSI</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_RX_PPDU_RSSI MiniportWdiRxPpduRssi;

void MiniportWdiRxPpduRssi(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  PNET_BUFFER_LIST pNBL,
  UINT8 *pRssi
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`pNBL`

Pointer to the <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> for which the RSSI is requested.

`*pRssi`

The absolute value of RSSI, in dB.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_RX_PPDU_RSSI callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>