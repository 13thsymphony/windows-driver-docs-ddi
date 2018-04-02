---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE
title: MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE
author: windows-driver-content
description: The MiniportWdiTalTxRxSetPortOpMode handler function specifies the opmode used for the port so that the TxEngine and RxEngine enable the corresponding functionality.
old-location: netvista\miniportwditaltxrxsetportopmode.htm
old-project: netvista
ms.assetid: 86F3005E-8BB3-4309-AFDE-7FA6E0427BFD
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE, MiniportWdiTalTxRxSetPortOpMode, MiniportWdiTalTxRxSetPortOpMode callback function [Network Drivers Starting with Windows Vista], dot11wdi/MiniportWdiTalTxRxSetPortOpMode, netvista.miniportwditaltxrxsetportopmode
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
-	MiniportWdiTalTxRxSetPortOpMode
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE callback function
The 
  MiniportWdiTalTxRxSetPortOpMode handler function specifies the opmode used for the port so that the TxEngine and RxEngine enable the corresponding functionality. It is called after the set-opmode command has been completed on the control path, but before a BSS is created (connect or start GO).

This is a WDI miniport handler inside <a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE MiniportWdiTalTxrxSetPortOpmode;

void MiniportWdiTalTxrxSetPortOpmode(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  WDI_PORT_ID PortId,
  WDI_OPERATION_MODE Opmode
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="https://msdn.microsoft.com/C297D681-D43F-4105-9E08-7FF42807E9A0">MiniportWdiTalTxRxInitialize</a>.

`PortId`

Port ID for the port.

`Opmode`

<a href="https://msdn.microsoft.com/library/windows/hardware/dn926085">WDI_OPERATION_MODE</a> value that specifies the operation mode for the port.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows Server 2016 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297618">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn926085">WDI_OPERATION_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>