---
UID: NS.netdma._NET_DMA_PROVIDER_ATTRIBUTES
title: NET_DMA_PROVIDER_ATTRIBUTES
author: windows-driver-content
description: The NET_DMA_PROVIDER_ATTRIBUTES structure specifies the configuration attributes for a NetDMA provider.
old-location: netvista\net_dma_provider_attributes.htm
ms.assetid: 7b5a7e9e-b10b-4c94-80b1-172cd9f0c9ca
ms.author: windowsdriverdev
ms.date: 11/1/2017
ms.topic: struct
ms.prod: windows-hardware
ms.technology: netvista
req.header: netdma.h
req.include-header: Netdma.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NetDMA 2.0 drivers in Windows Server 2008. Supported for NetDMA 1.1
   drivers in Windows Server 2008. Supported for NetDMA 1.0 drivers in Windows Server 2008 and Windows
   Vista.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: NET_DMA_PROVIDER_ATTRIBUTES
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
ms.keywords: NET_DMA_PROVIDER_ATTRIBUTES, NET_DMA_PROVIDER_ATTRIBUTES, *PNET_DMA_PROVIDER_ATTRIBUTES
req.iface: 
---

# NET_DMA_PROVIDER_ATTRIBUTES structure



## -description

## -syntax

````
typedef struct _NET_DMA_PROVIDER_ATTRIBUTES {
  UCHAR            MajorHwVersion;
  UCHAR            MinorHwVersion;
  USHORT           Size;
  ULONG            Flags;
  ULONG            VendorId;
  ULONG            DmaChannelCount;
  ULONG            MaximumTransferSize;
  PHYSICAL_ADDRESS MaximumAddressSpace;
} NET_DMA_PROVIDER_ATTRIBUTES, *PNET_DMA_PROVIDER_ATTRIBUTES;
````


## -struct-fields
<dl>

### -field <b>MajorHwVersion</b>

<dd>
<p>The major version number of the DMA provider hardware.</p>
</dd>

### -field <b>MinorHwVersion</b>

<dd>
<p>The minor version number of the DMA provider hardware.</p>
</dd>

### -field <b>Size</b>

<dd>
<p>The size, in bytes, of this NET_DMA_PROVIDER_ATTRIBUTES structure. Set this member to 
     sizeof(NET_DMA_PROVIDER_ATTRIBUTES).</p>
</dd>

### -field <b>Flags</b>

<dd>
<p>Reserved for DMA provider attributes flags. Set this member to zero.</p>
</dd>

### -field <b>VendorId</b>

<dd>
<p>A vendor identifier (ID) that uniquely identifies the vendor that created the DMA engine. This
     vendor ID is specified in the device's PCI configuration space. For more information about the vendor
     ID, see 
     <a href="devinst.identifiers_for_pci_devices">Identifiers for PCI
     Devices</a>.</p>
</dd>

### -field <b>DmaChannelCount</b>

<dd>
<p>The number of DMA channels that the DMA provider supports. This number can differ from the 
     <b>MaxDmaChannelCount</b> member of the 
     <a href="https://msdn.microsoft.com/7ec6d449-fdc2-44d8-976b-5a1d23c76e7b">
     NET_DMA_PROVIDER_CHARACTERISTICS</a> structure that defines the maximum number of DMA channels that
     this type of DMA provider can support.</p>
</dd>

### -field <b>MaximumTransferSize</b>

<dd>
<p>The maximum DMA transfer size, in bytes, that the DMA provider can support. This value can must be
     4 KB or greater.</p>
</dd>

### -field <b>MaximumAddressSpace</b>

<dd>
<p>The largest physical address that the DMA engine can support.</p>
</dd>
</dl>

## -remarks
<p>To start a DMA provider, the DMA provider driver supplies a NET_DMA_PROVIDER_ATTRIBUTES structure at
    the 
    <i>ProviderAttributes</i> parameter of the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568334">NetDmaProviderStart</a> function.</p>

<p>A DMA provider driver initializes a DMA engine and starts a DMA provider while handling the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a> IRP.</p>

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
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff551749">IRP_MN_START_DEVICE</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/7ec6d449-fdc2-44d8-976b-5a1d23c76e7b">
   NET_DMA_PROVIDER_CHARACTERISTICS</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568334">NetDmaProviderStart</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff568335">NetDmaProviderStop</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_DMA_PROVIDER_ATTRIBUTES structure%20 RELEASE:%20(11/1/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
