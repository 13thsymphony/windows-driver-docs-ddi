---
UID: NF:sercx.SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT
title: SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT function
author: windows-driver-content
description: The SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT function initializes a SERCX2_SYSTEM_DMA_RECEIVE_CONFIG structure.
old-location: serports\sercx2_system_dma_receive_config_init.htm
old-project: serports
ms.assetid: 9BD18E2C-731D-4C7D-8363-67136521B4A7
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: 2/SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT, SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT, SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT function [Serial Ports], serports.sercx2_system_dma_receive_config_init
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: sercx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.1.
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
req.irql: Any level.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	2.0\Sercx.h
api_name:
-	SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT
product: Windows
targetos: Windows
req.typenames: SERCX_STATUS, *PSERCX_STATUS
req.product: Windows 10 or later.
---


# SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT function
The <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</b> function initializes a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure.

## Syntax

```
void SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT(
  SERCX2_SYSTEM_DMA_RECEIVE_CONFIG *Config,
  size_t                           MaximumTransferLength,
  PHYSICAL_ADDRESS                 Address,
  DMA_WIDTH                        DmaWidth,
  PCM_PARTIAL_RESOURCE_DESCRIPTOR  DmaDescriptor
);
```

## Parameters

`Config`

A pointer to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure that is to be initialized.

`MaximumTransferLength`

The value to load into the <b>MaximumTransferLength</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`Address`

The value to load into the <b>DeviceAddress</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`DmaWidth`

The value to load into the <b>DmaWidth</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.

`DmaDescriptor`

The value to load into the <b>DmaDescriptor</b> member of the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b> structure. For more information, see the description of this member in <a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>.


## Return Value

None.

## Remarks

Your serial controller driver must use either this function or the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265341">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a> function to initialize a <a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a> structure before passing a pointer to this structure as an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/dn265279">SerCx2SystemDmaReceiveCreate</a> method.

<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</b> sets the <b>Size</b> member of the structure to <b>sizeof</b>(<b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</b>), and sets four additional members of the structure to the values supplied as input parameters to the function. The function sets the other members of the structure to zero. The driver can, if necessary, explicitly set these other members to nonzero values after the <b>SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT</b> call.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8.1.  |
| **Target Platform** | Desktop |
| **Header** | sercx.h |
| **IRQL** | Any level. |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn265339">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265341">SERCX2_SYSTEM_DMA_RECEIVE_CONFIG_INIT_NEW_DATA_NOTIFICATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/dn265279">SerCx2SystemDmaReceiveCreate</a>