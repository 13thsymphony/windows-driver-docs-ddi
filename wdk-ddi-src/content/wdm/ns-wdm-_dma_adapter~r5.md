---
UID: NS.WDM._DMA_ADAPTER~R5
title: _DMA_ADAPTER
author: windows-driver-content
description: The DMA_ADAPTER structure describes a system-defined interface to a DMA controller for a given device. A driver calls IoGetDmaAdapter to obtain this structure.
old-location: kernel\dma_adapter.htm
old-project: kernel
ms.assetid: 08cd5b10-725e-4a36-b70d-42a831b79372
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _DMA_ADAPTER, DMA_ADAPTER, *PADAPTER_OBJECT, *PDMA_ADAPTER
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DMA_ADAPTER
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
req.product: Windows 10 or later.
---

# _DMA_ADAPTER structure



## -description
The <b>DMA_ADAPTER</b> structure describes a system-defined interface to a DMA controller for a given device. A driver calls <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> to obtain this structure.



## -syntax

````
typedef struct _DMA_ADAPTER {
  USHORT          Version;
  USHORT          Size;
  PDMA_OPERATIONS DmaOperations;
} DMA_ADAPTER, *PDMA_ADAPTER;
````


## -struct-fields

### -field Version

Specifies the version of this structure. Version 3 of the <b>DMA_ADAPTER</b> structure is available starting with Windows 8. For versions 1 and 2 of this structure, this member is set to the value 1. For more information, see the following Remarks section.


### -field Size

Specifies the size, in bytes, of this structure.


### -field DmaOperations

Pointer to a <a href="kernel.dma_operations">DMA_OPERATIONS</a> structure that contains pointers to DMA adapter functions. The version of the <b>DMA_OPERATIONS</b> structure that this member points to is determined by the version of the <b>DMA_ADAPTER</b> structure. Thus, for version 1 of the <b>DMA_ADAPTER</b> structure, <i>DmaOperations</i> points to version 1 of the <b>DMA_OPERATIONS</b> structure, and so on. For more information about structure versions, see the following Remarks section.


## -remarks
Drivers for devices that use DMA to transfer data use this structure to obtain the addresses of functions that enable use of a DMA controller. Usually, drivers obtain this structure by calling the <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> routine. Drivers can also obtain this structure by querying for the <a href="kernel.bus_interface_standard">BUS_INTERFACE_STANDARD</a> interface.


## -requirements
<table>
<tr>
<th width="30%">
Header

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
<a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="kernel.dma_operations">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="kernel.bus_interface_standard">BUS_INTERFACE_STANDARD</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20DMA_ADAPTER structure%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

