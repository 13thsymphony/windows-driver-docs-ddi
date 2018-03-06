---
UID: NF:netdma.NetDmaProviderStart
title: NetDmaProviderStart function
author: windows-driver-content
description: The NetDmaProviderStart function notifies the NetDMA interface that all of the DMA channels that are associated with a DMA provider are initialized and ready for DMA transfers.
old-location: netvista\netdmaproviderstart.htm
old-project: netvista
ms.assetid: e99ebbe8-8605-4bf2-9ec0-d7cde25058f7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: NetDmaProviderStart, NetDmaProviderStart function [Network Drivers Starting with Windows Vista], netdma/NetDmaProviderStart, netdma_ref_bdb7c400-1c73-4dcb-8eb2-4121172302ad.xml, netvista.netdmaproviderstart
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
req.lib: NtosKrnl.exe
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
-	NetDmaProviderStart
product: Windows
targetos: Windows
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---


# NetDmaProviderStart function
<div class="alert"><b>Note</b>  The NetDMA interface is not supported 

in Windows 8 and later.</div><div> </div>The 
  <b>NetDmaProviderStart</b> function notifies the NetDMA interface that all of the DMA channels that are
  associated with a DMA provider are initialized and ready for DMA transfers.

## Syntax

````
VOID NetDmaProviderStart(
  _In_ PVOID                        NetDmaProviderHandle,
  _In_ PNET_DMA_PROVIDER_ATTRIBUTES ProviderAttributes
);
````

## Parameters

`NetDmaProviderHandle`

A handle that identifies a DMA provider. The DMA provider driver received this handle from the
     NetDMA interface in a call to the 
     <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">
     NetDmaRegisterProvider</a> function.

`ProviderAttributes`

A pointer to a 
     <a href="..\netdma\ns-netdma-_net_dma_provider_attributes.md">
     NET_DMA_PROVIDER_ATTRIBUTES</a> structure that defines the DMA device attributes of the DMA
     provider.


## Return Value

None

## Remarks

DMA providers call the 
    <b>NetDmaProviderStart</b> function to notify the NetDMA interface that a DMA provider is started. A DMA
    provider driver initializes a DMA engine and calls the 
    <b>NetDmaProviderStart</b> function while handling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP.

The DMA provider driver can also call 
    <b>NetDmaProviderStart</b> after the driver called the 
    <a href="..\netdma\nf-netdma-netdmaproviderstop.md">NetDmaProviderStop</a> function for
    application-specific reasons. DMA provider drivers call 
    <b>NetDmaProviderStop</b> to notify the NetDMA interface that a previously started DMA provider is no
    longer available.

The DMA provider driver supplies a 
    <a href="..\netdma\ns-netdma-_net_dma_provider_attributes.md">
    NET_DMA_PROVIDER_ATTRIBUTES</a> structure at the 
    <i>ProviderAttributes</i> parameter of 
    <b>NetDmaProviderStart</b>. The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration
    attributes for a NetDMA provider.

Before a DMA provider driver calls 
    <b>NetDmaProviderStart</b>, it should be ready to handle all NetDMA interface requests, such as
    allocating DMA channels and performing DMA transfers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported for NetDMA 1.0 drivers in Windows Vista.  |
| **Target Platform** | Universal |
| **Header** | netdma.h (include Netdma.h) |
| **Library** | NtosKrnl.exe |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\netdma\nf-netdma-netdmaproviderstop.md">NetDmaProviderStop</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>



<a href="..\netdma\ns-netdma-_net_dma_provider_attributes.md">NET_DMA_PROVIDER_ATTRIBUTES</a>



<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NetDmaProviderStart function%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>