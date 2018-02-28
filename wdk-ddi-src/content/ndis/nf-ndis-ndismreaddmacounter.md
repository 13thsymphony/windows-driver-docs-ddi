---
UID: NF:ndis.NdisMReadDmaCounter
title: NdisMReadDmaCounter function
author: windows-driver-content
description: The NdisMReadDmaCounter function returns the current value of the system DMA controller's counter.
old-location: netvista\ndismreaddmacounter.htm
old-project: netvista
ms.assetid: bfce0f28-4cca-48a2-8836-2f77f4b6370a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisMReadDmaCounter, NdisMReadDmaCounter function [Network Drivers Starting with Windows Vista], dma_ref_12d2675f-d576-4a5d-9af0-42dfd63fd1da.xml, ndis/NdisMReadDmaCounter, netvista.ndismreaddmacounter
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMReadDmaCounter (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMReadDmaCounter (NDIS   5.1)) in Windows XP.
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
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMReadDmaCounter
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---


# NdisMReadDmaCounter function
The 
  <b>NdisMReadDmaCounter</b> function returns the current value of the system DMA controller's counter.

## Syntax

````
ULONG NdisMReadDmaCounter(
  _In_ NDIS_HANDLE MiniportDmaHandle
);
````

## Parameters

`MiniportDmaHandle`

The handle returned when the miniport driver called the 
     <a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">NdisMRegisterDmaChannel</a> function
     during initialization.


## Return Value

<b>NdisMReadDmaCounter</b> returns the number of bytes remaining in the current DMA transfer on the
     channel used by the NIC.

## Remarks

Miniport drivers of devices that use the system DMA controller's auto-initialize mode can call 
    <b>NdisMReadDmaCounter</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NDIS 6.0 and NDIS 5.1 drivers (see    NdisMReadDmaCounter (NDIS   5.1)) in Windows Vista. Supported for NDIS 5.1 drivers (see    NdisMReadDmaCounter (NDIS   5.1)) in Windows XP.  |
| **Target Platform** | Universal |
| **Header** | ndis.h (include Ndis.h) |
| **Library** | Ndis.lib |
| **IRQL** | "<= DISPATCH_LEVEL" |
| **DDI compliance rules** | Irql_Miniport_Driver_Function |

## See Also

<a href="..\ndis\nf-ndis-ndismregisterdmachannel.md">NdisMRegisterDmaChannel</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMReadDmaCounter function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>