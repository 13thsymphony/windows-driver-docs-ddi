---
UID: NS:wdm._DMA_TRANSFER_INFO
title: "_DMA_TRANSFER_INFO"
author: windows-driver-content
description: The DMA_TRANSFER_INFO structure is a container for a DMA_TRANSFER_INFO_XXX structure that describes the allocation requirements for a scatter/gather list.
old-location: kernel\dma_transfer_info.htm
old-project: kernel
ms.assetid: 1CD5CE6F-5179-40D5-BCD9-3587914C8139
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: "*PDMA_TRANSFER_INFO, DMA_TRANSFER_INFO, DMA_TRANSFER_INFO structure [Kernel-Mode Driver Architecture], PDMA_TRANSFER_INFO, PDMA_TRANSFER_INFO structure pointer [Kernel-Mode Driver Architecture], _DMA_TRANSFER_INFO, kernel.dma_transfer_info, wdm/DMA_TRANSFER_INFO, wdm/PDMA_TRANSFER_INFO"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Wdm.h
api_name:
-	DMA_TRANSFER_INFO
product: Windows
targetos: Windows
req.typenames: DMA_TRANSFER_INFO, *PDMA_TRANSFER_INFO
req.product: Windows 10 or later.
---

# _DMA_TRANSFER_INFO structure
The <b>DMA_TRANSFER_INFO</b> structure is a container for a <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure that describes the allocation requirements for a scatter/gather list.

## Syntax
````
typedef struct _DMA_TRANSFER_INFO {
  ULONG  Version;
  union {
    DMA_TRANSFER_INFO_V1 V1;
  };
} DMA_TRANSFER_INFO, *PDMA_TRANSFER_INFO;
````

## Members


`Version`

The version number of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure that follows this member. For a <a href="..\wdm\ns-wdm-_dma_transfer_info_v1.md">DMA_TRANSFER_INFO_V1</a> structure, set this member to DMA_TRANSFER_INFO_VERSION1 before calling the <a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a> routine.

## Remarks
A device driver calls the <a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a> routine to obtain a <b>DMA_TRANSFER_INFO</b> structure that describes the allocation requirements for the scatter/gather list to use in a DMA transfer.

The unnamed union in this structure contains a <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure. The <b>Version</b> member indicates which version of the <b>DMA_TRANSFER_INFO_<i>XXX</i></b> structure is contained in the union. Currently, only version 1 is supported.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Supported starting with Windows 8. Supported starting with Windows 8. |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |

## See Also

<a href="..\wdm\ns-wdm-_dma_transfer_info_v1.md">DMA_TRANSFER_INFO_V1</a>



<a href="..\wdm\nc-wdm-pget_dma_transfer_info.md">GetDmaTransferInfo</a>