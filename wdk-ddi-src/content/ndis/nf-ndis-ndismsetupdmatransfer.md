---
UID: NF:ndis.NdisMSetupDmaTransfer
title: NdisMSetupDmaTransfer macro
author: windows-driver-content
description: The NdisMSetupDmaTransfer function sets up the host DMA controller for a DMA transfer.
old-location: netvista\ndismsetupdmatransfer.htm
old-project: netvista
ms.assetid: 2a7ebedd-0042-4624-9c9b-721cccfb0c4f
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ndis/NdisMSetupDmaTransfer, netvista.ndismsetupdmatransfer, dma_ref_b6de5799-dca5-4c30-aa3a-e20e1eac4f0f.xml, NdisMSetupDmaTransfer, NdisMSetupDmaTransfer macro [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMSetupDmaTransfer (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMSetupDmaTransfer (NDIS   5.1)) in Windows XP.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: ndis.h
req.dll: 
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ndis.h
apiname:
-	NdisMSetupDmaTransfer
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---


# NdisMSetupDmaTransfer function
The 
  <b>NdisMSetupDmaTransfer</b> function sets up the host DMA controller for a DMA transfer.

## Syntax

````
VOID NdisMSetupDmaTransfer(
  [out] PNDIS_STATUS Status,
  [in]  NDIS_HANDLE  MiniportDmaHandle,
  [in]  PNDIS_BUFFER Buffer,
  [in]  ULONG        Offset,
  [in]  ULONG        Length,
  [in]  BOOLEAN      WriteToDevice
);
````

## Parameters

`_S`

TBD

`_H`

TBD

`_B`

TBD

`_O`

TBD

`_L`

TBD

`_M_`

TBD


## Return Value

None

## Remarks

Drivers of subordinate-DMA NICs call 
    <b>NdisMSetupDmaTransfer</b> in response to incoming send requests, for which the driver sets 
    <i>WriteToDevice</i> to <b>TRUE</b>. They set 
    <i>WriteToDevice</i> to <b>FALSE</b> when they transfer received data from the NIC to host memory.

The caller of 
    <b>NdisMSetupDmaTransfer</b> supplies a buffer descriptor mapping the host memory range that is the target
    of the transfer or that contains data for a download operation from the host to the NIC. To specify a
    transfer sized to suit the DMA constraints of the NIC, the caller can set up a subrange to be transferred
    with the 
    <i>Offset</i> and 
    <i>Length</i> parameters if necessary.

The caller must supply a buffer descriptor that specifies the host range into which received data will
    be transferred from the NIC when 
    <i>WriteToDevice</i> is <b>FALSE</b>. Otherwise, the buffer descriptor at 
    <i>Buffer</i> was chained to a packet descriptor input to the miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">
    MiniportSendNetBufferLists</a> function.

To improve performance for small transmit requests, such as a send request of less than 256 bytes in
    length, a miniport driver can copy the packet data into an internal staging buffer and pass a
    driver-allocated buffer descriptor mapping that buffer to 
    <b>NdisMSetupDmaTransfer</b>.

On return from 
    <b>NdisMSetupDmaTransfer</b>, the host DMA controller has been programmed for the transfer. The miniport
    driver then programs the NIC for the transfer operation.

When the transfer is complete, the miniport driver must call the 
    <a href="..\ndis\nf-ndis-ndismcompletedmatransfer.md">
    NdisMCompleteDmaTransfer</a> function.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMSetupDmaTransfer (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMSetupDmaTransfer (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | ndis.h |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miniport_Driver_Function |

## See Also

<a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">NdisMRegisterDmaChannel</a>



<a href="..\ndis\nf-ndis-ndismcompletedmatransfer.md">NdisMCompleteDmaTransfer</a>



<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMSetupDmaTransfer macro%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>