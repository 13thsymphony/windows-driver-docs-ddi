---
UID: NC:dot11wdi.MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE
title: MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE
author: windows-driver-content
description: The MiniportWdiTalTxRxSetPortOpMode handler function specifies the opmode used for the port so that the TxEngine and RxEngine enable the corresponding functionality.
old-location: netvista\miniportwditaltxrxsetportopmode.htm
old-project: netvista
ms.assetid: 86F3005E-8BB3-4309-AFDE-7FA6E0427BFD
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwditaltxrxsetportopmode, MiniportWdiTalTxRxSetPortOpMode callback function [Network Drivers Starting with Windows Vista], MiniportWdiTalTxRxSetPortOpMode, MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE, MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE, dot11wdi/MiniportWdiTalTxRxSetPortOpMode
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
-	MiniportWdiTalTxRxSetPortOpMode
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---


# MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE callback function
The 
  MiniportWdiTalTxRxSetPortOpMode handler function specifies the opmode used for the port so that the TxEngine and RxEngine enable the corresponding functionality. It is called after the set-opmode command has been completed on the control path, but before a BSS is created (connect or start GO).

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
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

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`PortId`

Port ID for the port.

`Opmode`

<a href="..\dot11wdi\ne-dot11wdi-_wdi_operation_mode.md">WDI_OPERATION_MODE</a> value that specifies the operation mode for the port.


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



<a href="https://msdn.microsoft.com/5B40171C-4E5F-4C35-A6E7-1EA5181C02E8">WDI general datapath interfaces</a>



<a href="..\dot11wdi\ne-dot11wdi-_wdi_operation_mode.md">WDI_OPERATION_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TAL_TXRX_SET_PORT_OPMODE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>