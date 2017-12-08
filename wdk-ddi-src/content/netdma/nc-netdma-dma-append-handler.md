---
UID: NC.netdma.DMA_APPEND_HANDLER
title: DMA_APPEND_HANDLER
author: windows-driver-content
description: The ProviderAppendDma function appends a linked list of DMA descriptors to the last descriptor on a DMA channel.
old-location: netvista\providerappenddma.htm
old-project: netvista
ms.assetid: 51de8ddf-cbfc-4e49-b44a-207307a937e7
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: MIRACAST_WFD_CONNECTION_STATS, MIRACAST_WFD_CONNECTION_STATS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 drivers in Windows Server 2008. Supported for NetDMA 1.1   drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in Windows Server 2008 and Windows   Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: ProviderAppendDma
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
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# DMA_APPEND_HANDLER callback



## -description

## -prototype

````
DMA_APPEND_HANDLER ProviderAppendDma;

NTSTATUS ProviderAppendDma(
  _In_ PVOID               ProviderChannelContext,
  _In_ PNET_DMA_DESCRIPTOR DescriptorVirtualAddress,
  _In_ PHYSICAL_ADDRESS    DescriptorPhysicalAddress,
  _In_ ULONG               DescriptorCount
)
{ ... }
````


## -parameters
<dl>

### -param ProviderChannelContext [in]

<dd>
<p>A pointer that identifies a DMA channel's context area. The DMA provider returned this handle to
     NetDMA at the location that is specified in the 
     <i>pProviderChannelContext</i> parameter of the 
     <a href="..\netdma\nc-netdma-dma-channel-allocate-handler.md">
     ProviderAllocateDmaChannel</a> function.</p>
</dd>

### -param DescriptorVirtualAddress [in]

<dd>
<p>A pointer to the virtual address of the first 
     <a href="..\netdma\ns-netdma--net-dma-descriptor.md">NET_DMA_DESCRIPTOR</a> structure in a linked
     list of DMA descriptors. The corresponding physical address is specified at the 
     <i>DescriptorPhysicalAddress</i> parameter.</p>
</dd>

### -param DescriptorPhysicalAddress [in]

<dd>
<p>A pointer to the physical address of the first DMA descriptor in a linked list of DMA descriptors.
     The corresponding virtual address is specified at the 
     <i>DescriptorVirtualAddress</i> parameter.</p>
</dd>

### -param DescriptorCount [in]

<dd>
<p>The number of DMA descriptors at 
     <i>DescriptorVirtualAddress</i> .
     </p>
<div class="alert"><b>Note</b>  NetDMA provider drivers prior to NetDMA version 2.0 can ignore the 
     <i>DescriptorCount</i> parameter. For NetDMA 2.0 and later versions, this parameter is the count of
     descriptors in the DMA operation.</div>
<div> </div>
</dd>
</dl>

## -returns
<p><i>ProviderAppendDma</i> returns one of the following status values:</p><dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl><p>The operation completed successfully.</p><dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl><p>The operation failed for unspecified reasons.</p>

<p> </p>

## -remarks
<p>The NetDMA interface calls a DMA provider driver's 
    <i>ProviderAppendDma</i> function to append a linked list of DMA descriptors after the last descriptor on
    a DMA channel. The NetDMA interface can call 
    <i>ProviderAppendDma</i> any number of times after a DMA transfer is started. However, the NetDMA
    interface must call the 
    <a href="..\netdma\nc-netdma-dma-start-handler.md">ProviderStartDma</a> function after a channel
    reset or abort, or after the DMA channel is first allocated.</p>

<p>The NetDMA interface sets the 
    <b>NextDescriptor</b> member of the last descriptor to the beginning of the new chain of descriptors
    before calling 
    <i>ProviderAppendDma</i>.</p>

<p>If the current descriptor in an active transfer is the last descriptor, the DMA engine must reread the
    last descriptor. The 
    <b>NextDescriptor</b> member in the last 
    <a href="..\netdma\ns-netdma--net-dma-descriptor.md">NET_DMA_DESCRIPTOR</a> structure should have
    a new address, and the DMA engine should continue with the next descriptor. If the current descriptor is
    not the last descriptor, the DMA engine can continue processing DMA descriptors with no additional
    tasks.</p>

<p>NetDMA calls 
    <i>ProviderAppendDma</i> at IRQL &lt;= DISPATCH_LEVEL.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported for NetDMA 2.0 drivers in Windows Server 2008. Supported for NetDMA 1.1
   drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in Windows Server 2008 and Windows
   Vista.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Netdma.h (include Netdma.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>&lt;= DISPATCH_LEVEL</p>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="..\netdma\ns-netdma--net-dma-descriptor.md">NET_DMA_DESCRIPTOR</a>
</dt>
<dt>
<a href="..\netdma\nc-netdma-dma-channel-allocate-handler.md">ProviderAllocateDmaChannel</a>
</dt>
<dt>
<a href="..\netdma\nc-netdma-dma-start-handler.md">ProviderStartDma</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20DMA_APPEND_HANDLER callback function%20 RELEASE:%20(11/30/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
