---
UID: NS.wdm._DMA_TRANSFER_INFO
title: DMA_TRANSFER_INFO
author: windows-driver-content
description: The DMA_TRANSFER_INFO structure is a container for a DMA_TRANSFER_INFO_XXX structure that describes the allocation requirements for a scatter/gather list.
old-location: kernel\dma_transfer_info.htm
old-project: kernel
ms.assetid: 1CD5CE6F-5179-40D5-BCD9-3587914C8139
ms.author: windowsdriverdev
ms.date: 11/28/2017
ms.keywords: DMA_TRANSFER_INFO, DMA_TRANSFER_INFO, *PDMA_TRANSFER_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DMA_TRANSFER_INFO
req.alt-loc: Wdm.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.iface: 
req.product: Windows 10 or later.
---

# DMA_TRANSFER_INFO structure



## -description
<p>The <b>DMA_TRANSFER_INFO</b> structure is a container for a <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure that describes the allocation requirements for a scatter/gather list.</p>


## -syntax

````
typedef struct _DMA_TRANSFER_INFO {
  ULONG  Version;
  union {
    DMA_TRANSFER_INFO_V1 V1;
  };
} DMA_TRANSFER_INFO, *PDMA_TRANSFER_INFO;
````


## -struct-fields
<dl>

### -field <b>Version</b>

<dd>
<p>The version number of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure that follows this member. For a <a href="..\wdm\ns-wdm--dma-transfer-info-v1.md">DMA_TRANSFER_INFO_V1</a> structure, set this member to DMA_TRANSFER_INFO_VERSION1 before calling the <a href="kernel.getdmatransferinfo">GetDmaTransferInfo</a> routine.</p>
</dd>

### -field <b>V1</b>

<dd>
<p>The allocation requirements for a scatter/gather list. For more information, see <a href="..\wdm\ns-wdm--dma-transfer-info-v1.md">DMA_TRANSFER_INFO_V1</a>.</p>
</dd>
</dl>

## -remarks
<p>A device driver calls the <a href="kernel.getdmatransferinfo">GetDmaTransferInfo</a> routine to obtain a <b>DMA_TRANSFER_INFO</b> structure that describes the allocation requirements for the scatter/gather list to use in a DMA transfer.</p>

<p>The unnamed union in this structure contains a <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure. The <b>Version</b> member indicates which version of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure is contained in the union. Currently, only version 1 is supported.</p>

## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Wdm.h (include Wdm.h, Ntddk.h, or Ntifs.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.getdmatransferinfo">GetDmaTransferInfo</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm--dma-transfer-info-v1.md">DMA_TRANSFER_INFO_V1</a>
</dt>
</dl>
<p> </p>
<p> </p>
<p><a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_TRANSFER_INFO structure%20 RELEASE:%20(11/28/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a></p>
