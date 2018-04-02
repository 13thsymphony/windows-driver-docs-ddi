---
UID: NF:netdma.NetDmaDeregisterProvider
title: NetDmaDeregisterProvider function
author: windows-driver-content
description: The NetDmaDeregisterProvider function deregisters a DMA provider.
old-location: netvista\netdmaderegisterprovider.htm
old-project: netvista
ms.assetid: 8832adbc-c2ab-4742-94a0-4e33d03eaaf1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NetDmaDeregisterProvider, NetDmaDeregisterProvider function [Network Drivers Starting with Windows Vista], netdma/NetDmaDeregisterProvider, netdma_ref_0fac8a7e-7721-4854-8d0e-6926243ff2ea.xml, netvista.netdmaderegisterprovider
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 1.0 drivers in Windows Vista.
req.target-min-winversvr: 
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	netdma.h
api_name:
-	NetDmaDeregisterProvider
product:
- Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---


# NetDmaDeregisterProvider function
<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaDeregisterProvider</b> function deregisters a DMA provider.

## Syntax

```
NET_DMA_EXPORT VOID NetDmaDeregisterProvider(
  PVOID NetDmaProviderHandle
);
```

## Parameters

`NetDmaProviderHandle`

A handle that identifies a DMA provider. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="https://msdn.microsoft.com/35d70d0b-c1b9-433f-941d-6cb61ddf0b62">
     NetDmaRegisterProvider</a> function.


## Return Value

None

## Remarks

DMA provider drivers call the 
    <b>NetDmaDeregisterProvider</b> function to deregister a DMA provider that was previously registered by
    calling the 
    <a href="https://msdn.microsoft.com/35d70d0b-c1b9-433f-941d-6cb61ddf0b62">
    NetDmaRegisterProvider</a> function.

The DMA provider driver must call the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568335">NetDmaProviderStop</a> function before it
    deregisters a DMA provider. The DMA provider driver calls 
    <b>NetDmaProviderStop</b> to notify the NetDMA interface that a previously started DMA provider is no
    longer available.

A DMA provider driver typically calls the 
    <b>NetDmaDeregisterProvider</b> function in the context of processing the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a> IRP for the DMA
    provider.

Call 
    <b>NetDmaDeregisterProvider</b> at IRQL = PASSIVE_LEVEL.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NetDMA 1.0 drivers in Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | netdma.h (include Netdma.h) |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff551738">IRP_MN_REMOVE_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568335">NetDmaProviderStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568336">NetDmaRegisterProvider</a>