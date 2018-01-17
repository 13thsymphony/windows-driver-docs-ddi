---
UID: NF:netdma.NetDmaPnPEventNotify
title: NetDmaPnPEventNotify function
author: windows-driver-content
description: The NetDmaPnPEventNotify function indicates a power state change for a NetDMA provider device.
old-location: netvista\netdmapnpeventnotify.htm
old-project: netvista
ms.assetid: a0f0fdbc-089c-4bfb-ba5f-eaff6042621c
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: NetDmaPnPEventNotify
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Universal
req.target-min-winverclnt: Supported for NetDMA 2.0 and NetDMA 1.1 drivers in Windows Server 2008.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NetDmaPnPEventNotify
req.alt-loc: netdma.h
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
req.typenames: NET_DMA_PNP_NOTIFICATION_CODE, *PNET_DMA_PNP_NOTIFICATION_CODE
---

# NetDmaPnPEventNotify function



## -description

## -syntax

````
VOID NetDmaPnPEventNotify(
  _In_ PVOID                     NetDmaProviderHandle,
  _In_ PNET_DMA_PNP_NOTIFICATION PnPEvent
);
````


## -parameters

### -param NetDmaProviderHandle [in]

A handle that identifies a DMA provider. A DMA provider driver receives this handle from the
     NetDMA interface in a call to the 
     <a href="..\netdma\nf-netdma-netdmaregisterprovider.md">
     NetDmaRegisterProvider</a> function.


### -param PnPEvent [in]

A pointer to a 
     <a href="..\netdma\ns-netdma-_net_dma_pnp_notification.md">NET_DMA_PNP_NOTIFICATION</a> structure
     that specifies a NetDMA PnP and power management event.


## -returns
This function does not return a value.


## -remarks
NetDMA provider drivers call the 
    <b>NetDmaPnPEventNotify</b> function to indicate a power state change for a NetDMA provider device.

To send a power management notification to the NetDMA interface, NetDMA provider drivers call the 
    <b>NetDmaPnPEventNotify</b> function and provide a pointer to a 
    <a href="..\netdma\ns-netdma-_net_dma_pnp_notification.md">NET_DMA_PNP_NOTIFICATION</a> structure
    at the 
    <i>PnPEvent</i> parameter.

A NetDMA provider driver calls 
    <b>NetDmaPnPEventNotify</b> at IRQL = PASSIVE_LEVEL.


## -see-also
<dl>
<dt>
<a href="..\netdma\nf-netdma-netdmaregisterprovider.md">NetDmaRegisterProvider</a>
</dt>
<dt>
<a href="..\netdma\ns-netdma-_net_dma_pnp_notification.md">NET_DMA_PNP_NOTIFICATION</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NetDmaPnPEventNotify function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

