---
UID: NF:ndis.NdisMDeregisterDmaChannel
title: NdisMDeregisterDmaChannel function
author: windows-driver-content
description: The NdisMDeregisterDmaChannel function releases a miniport driver's claim on a DMA channel for a NIC.
old-location: netvista\ndismderegisterdmachannel.htm
old-project: netvista
ms.assetid: 1581cbfd-bdab-40ed-9978-f60ec220c17a
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMDeregisterDmaChannel, NdisMDeregisterDmaChannel function [Network Drivers Starting with Windows Vista], dma_ref_8babcd45-1946-4928-a0a2-2fc0871b9f90.xml, ndis/NdisMDeregisterDmaChannel, netvista.ndismderegisterdmachannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMDeregisterDmaChannel (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMDeregisterDmaChannel (NDIS   5.1)) in Windows XP.
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
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMDeregisterDmaChannel
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMDeregisterDmaChannel function
The 
  <b>NdisMDeregisterDmaChannel</b> function releases a miniport driver's claim on a DMA channel for a
  NIC.

## Syntax

````
VOID NdisMDeregisterDmaChannel(
  _In_ NDIS_HANDLE MiniportDmaHandle
);
````

## Parameters

`MiniportDmaHandle`

The DMA handle returned by the 
     <a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">
     NdisMRegisterDmaChannel</a> function.


## Return Value

None

## Remarks

The caller should consider 
    <i>MiniportDmaHandle</i> invalid as soon as it is passed to 
    <b>NdisMDeregisterDmaChannel</b>. This function releases the NIC's claim on the DMA channel in the
    registry.

<b>NdisMDeregisterDmaChannel</b> can be called only from a miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> and 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> functions.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMDeregisterDmaChannel (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMDeregisterDmaChannel (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | PASSIVE_LEVEL |
| **DDI compliance rules** | Irql_Miniport_Driver_Function |

## See Also

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>



<a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">NdisMRegisterDmaChannel</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMDeregisterDmaChannel function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>