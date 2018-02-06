---
UID: NC:dot11wdi.MINIPORT_WDI_RX_RESUME
title: MINIPORT_WDI_RX_RESUME
author: windows-driver-content
description: The MiniportWdiRxResume handler function is issued by the RxMgr after it returns a pause status to a data indication.
old-location: netvista\miniportwdirxresume.htm
old-project: netvista
ms.assetid: 483C59C3-8F9C-48A5-B5E4-34A60BAE1B1A
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwdirxresume, MiniportWdiRxResume callback function [Network Drivers Starting with Windows Vista], MiniportWdiRxResume, MINIPORT_WDI_RX_RESUME, MINIPORT_WDI_RX_RESUME, dot11wdi/MiniportWdiRxResume
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
-	MiniportWdiRxResume
product: Windows
targetos: Windows
req.typenames: SYNTH_STATS, *PSYNTH_STATS
---


# MINIPORT_WDI_RX_RESUME callback function
The 
  MiniportWdiRxResume handler function is issued by the RxMgr after it returns a pause status to a data indication. The RxEngine can  immediately resume creating data indications, either in the same context as the MiniportWdiRxResume or from a different thread.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_RX_RESUME</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_RX_RESUME MiniportWdiRxResume;

void MiniportWdiRxResume(
  TAL_TXRX_HANDLE MiniportTalTxRxContext
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.


## Return Value

This callback function does not return a value.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>

<a href="https://msdn.microsoft.com/EEEA7181-4A24-4F40-8A44-65EC38D1A867">WDI RX path</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_RX_RESUME callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>