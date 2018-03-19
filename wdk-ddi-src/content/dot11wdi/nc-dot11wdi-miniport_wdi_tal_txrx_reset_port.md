---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_RESET_PORT
title: MINIPORT_WDI_TAL_TXRX_RESET_PORT
author: windows-driver-content
description: The MiniportWdiTalTxRxResetPort handler function is invoked before a dot11 reset task is issued to the target.
old-location: netvista\miniportwditaltxrxresetport.htm
old-project: netvista
ms.assetid: BB584FC9-8048-42F4-AFA9-7BF6790EDD69
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_RESET_PORT, MiniportWdiTalTxRxResetPort, MiniportWdiTalTxRxResetPort callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxResetPort, netvista.miniportwditaltxrxresetport
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
-	MiniportWdiTalTxRxResetPort
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_TAL_TXRX_RESET_PORT callback function
The 
  MiniportWdiTalTxRxResetPort handler function is invoked before a dot11 reset task is issued to the target.  The functional components RXEngine/TxEngine have already stopped operations associated with this port and any pending data frames have been completed/returned. It allows the TX/RX components to clear  the port state. This does not involve changing the operation mode.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_RESET_PORT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_TAL_TXRX_RESET_PORT MiniportWdiTalTxrxResetPort;

void MiniportWdiTalTxrxResetPort(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  WDI_PORT_ID PortId
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`PortId`

Port ID for the port being reset.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>