---
UID : NC:wdm.PPUT_DMA_ADAPTER
title : PPUT_DMA_ADAPTER
author : windows-driver-content
description : The PutDmaAdapter routine frees a DMA_ADAPTER structure previously allocated by IoGetDmaAdapter.
old-location : kernel\putdmaadapter.htm
old-project : kernel
ms.assetid : 05a76baf-e5f7-41ca-ac9f-4538cd3e0292
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 2000.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : PutDmaAdapter
req.alt-loc : wdm.h
req.ddi-compliance : IrqlDispatch
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : <= DISPATCH_LEVEL
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
---


# PPUT_DMA_ADAPTER callback function
The <b>PutDmaAdapter</b> routine frees a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure previously allocated by <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

## Syntax

```
PPUT_DMA_ADAPTER PputDmaAdapter;

void PputDmaAdapter(
  PDMA_ADAPTER DmaAdapter
)
{...}
```

## Parameters

`DmaAdapter`

Pointer to the <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure to be released.


## Return Value

None

## Remarks

<b>PutDmaAdapter</b>
           is not a system routine that can be called directly by name. This routine is callable only by pointer from the address returned in a 
          <a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
           structure. Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>.

<b>PutDmaAdapter</b> frees a DMA adapter object previously allocated by <b>IoGetDmaAdapter</b>. Drivers should call <b>PutDmaAdapter</b> after completing DMA operations and freeing any map registers and common buffer allocated with this adapter object. After <b>PutDmaAdapter</b> returns, the driver can no longer use the DMA adapter object.

A driver must call <b>PutDmaAdapter</b> when it receives a PnP <a href="https://msdn.microsoft.com/library/windows/hardware/ff551755">IRP_MN_STOP_DEVICE</a> request.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **Library** |  |
| **IRQL** | <= DISPATCH_LEVEL |
| **DDI compliance rules** | IrqlDispatch |

## See Also

<dl>
<dt>
<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>
</dt>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PPUT_DMA_ADAPTER callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>