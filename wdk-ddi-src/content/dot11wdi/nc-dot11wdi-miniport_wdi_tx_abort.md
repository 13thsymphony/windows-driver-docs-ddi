---
UID: NC:dot11wdi.MINIPORT_WDI_TX_ABORT
title: MINIPORT_WDI_TX_ABORT
author: windows-driver-content
description: The MiniportWdiTxAbort handler function aborts outstanding TX frames for a given port or peer, which includes initiating the completion of frames owned by the TAL/target.
old-location: netvista\miniportwditxabort.htm
old-project: netvista
ms.assetid: FA6BEAE9-5D48-463E-A398-518737D78867
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.miniportwditxabort, MiniportWdiTxAbort callback function [Network Drivers Starting with Windows Vista], MiniportWdiTxAbort, MINIPORT_WDI_TX_ABORT, MINIPORT_WDI_TX_ABORT, dot11wdi/MiniportWdiTxAbort
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
-	MiniportWdiTxAbort
product: Windows
targetos: Windows
req.typenames: "*PSYNTH_STATS, SYNTH_STATS"
---


# MINIPORT_WDI_TX_ABORT callback function
The 
  MiniportWdiTxAbort handler function aborts outstanding TX frames for a given port or peer, which includes initiating the completion of frames owned by the TAL/target. This request is issued to the TAL as part of handling <a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a> (adapter-wide TX abort), dot11 reset (port-wide abort), and after <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_delete_ind.md">NdisWdiPeerDeleteIndication</a> if WDI is operating in peer queuing mode.

This is a WDI miniport handler inside <a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_WDI_TX_ABORT</b> type. For more
   information, see the following Examples section.</div><div> </div>

## Syntax

```
MINIPORT_WDI_TX_ABORT MiniportWdiTxAbort;

void MiniportWdiTxAbort(
  TAL_TXRX_HANDLE MiniportTalTxRxContext,
  WDI_PORT_ID PortId,
  WDI_PEER_ID PeerId,
  NDIS_STATUS *pWifiStatus
)
{...}
```

## Parameters

`MiniportTalTxRxContext`

TAL device handle returned by the IHV miniport in <a href="..\dot11wdi\nc-dot11wdi-miniport_wdi_tal_txrx_initialize.md">MiniportWdiTalTxRxInitialize</a>.

`PortId`

The port ID.

`PeerId`

The peer ID.

`*pWifiStatus`

Pointer to a status of the MiniportWdiTxAbort, which should be set by the IHV miniport.  See the <i>Remarks</i> section for more information.


## Return Value

This callback function does not return a value.

## Remarks

A wildcard may be specified for the <i>PeerId</i> to stop TX on a port.

A wildcard for <i>PortId</i> and <i>PeerId</i> may be specified to stop TX across the adapter.

To complete the stop operation, the TAL must do the following steps.

<ol>
<li>Initiate the return of ownership of TX data buffers corresponding to the input parameters to the host. These frames should be completed by indicating transfer completion for all frames passed to the TxEngine in send requests and indicating <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a> for outstanding TX frames that require explicit send completion (if the TX frame was not transfer completed with a success code).</li>
<li>Return a success status, or return a pending status and issue <a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_abort_confirm.md">NdisWdiTxAbortConfirm</a> later.</li>
</ol>

#### Examples

To define a MiniportWdiTxAbort function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a MiniportWdiTxAbort function that is named "MyTxAbort", use the <b>MINIPORT_WDI_TX_ABORT</b> type as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>MINIPORT_WDI_TX_ABORT MyTxAbort;</pre>
</td>
</tr>
</table></span></div>
Then, implement your function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
 MyTxAbort(
    TAL_TXRX_HANDLE MiniportTalTxRxContext,
    WDI_PORT_ID PortId,
    WDI_PEER_ID PeerId,
    NDIS_STATUS *pWifiStatus
    )
  {...}</pre>
</td>
</tr>
</table></span></div>
The <b>MINIPORT_WDI_TX_ABORT</b> function type is defined in the dot11wdi.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_WDI_TX_ABORT</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/232c4272-0bf0-4a4e-9560-3bceeca8a3e3">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?linkid=286697">Annotating Function Behavior</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 10 Windows 10 |
| **Target Platform** | Windows |
| **Header** | dot11wdi.h |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/mt297658">WDI_PEER_ID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt297625">TAL_TXRX_HANDLE</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_peer_delete_ind.md">NdisWdiPeerDeleteIndication</a>



<a href="https://msdn.microsoft.com/8DF3E82E-761E-4A90-A789-1CB8EE8F0377">WDI TX path</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_abort_confirm.md">NdisWdiTxAbortConfirm</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt269099">WDI_PORT_ID</a>



<a href="..\dot11wdi\ns-dot11wdi-_ndis_miniport_wdi_data_handlers.md">NDIS_MINIPORT_WDI_DATA_HANDLERS</a>



<a href="..\dot11wdi\nc-dot11wdi-ndis_wdi_tx_send_complete_ind.md">NdisWdiTxSendCompleteIndication</a>



<a href="..\ndis\nc-ndis-miniport_pause.md">MiniportPause</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20MINIPORT_WDI_TX_ABORT callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>