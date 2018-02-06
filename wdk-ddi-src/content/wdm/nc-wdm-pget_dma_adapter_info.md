---
UID: NC:wdm.PGET_DMA_ADAPTER_INFO
title: PGET_DMA_ADAPTER_INFO
author: windows-driver-content
description: The GetDmaAdapterInfo routine retrieves information about the hardware capabilities of a system DMA channel.
old-location: kernel\getdmaadapterinfo.htm
old-project: kernel
ms.assetid: 2F502ACA-0CFF-46A1-B54C-1034D6E56815
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: kernel.getdmaadapterinfo, GetDmaAdapterInfo, GetDmaAdapterInfo callback function [Kernel-Mode Driver Architecture], GetDmaAdapterInfo, PGET_DMA_ADAPTER_INFO, PGET_DMA_ADAPTER_INFO, wdm/GetDmaAdapterInfo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: wdm.h
req.include-header: Wdm.h, Ntddk.h, Ntifs.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: "<= DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Wdm.h
apiname:
-	GetDmaAdapterInfo
product: Windows
targetos: Windows
req.typenames: WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product: Windows 10 or later.
---


# PGET_DMA_ADAPTER_INFO callback function
The <b>GetDmaAdapterInfo</b> routine retrieves information about the hardware capabilities of a system DMA channel.

## Syntax

```
PGET_DMA_ADAPTER_INFO PgetDmaAdapterInfo;

NTSTATUS PgetDmaAdapterInfo(
  PDMA_ADAPTER DmaAdapter,
  PDMA_ADAPTER_INFO AdapterInfo
)
{...}
```

## Parameters

`DmaAdapter`

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.

`AdapterInfo`

A pointer to a caller-allocated <a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER_INFO</a> structure. The routine writes information about the system DMA controller into this structure. The caller must set the
        <b>Version</b> member of this structure to DMA_ADAPTER_INFO_VERSION1 before calling <b>GetDmaAdapterInfo</b>.


## Return Value

<b>GetDmaAdapterInfo</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.
<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The routine does not support the specified version of the <b>DMA_ADAPTER_INFO_<i>XXX</i></b> structure.

</td>
</tr>
</table>

## Remarks

<b>GetDmaAdapterInfo</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>GetDmaAdapterInfo</b> retrieves the following information:
<ul>
<li>
The maximum number of elements in a scatter/gather list that the DMA controller can process in a single scatter/gather DMA operation.

</li>
<li>
The width, in bits, of a DMA address.

</li>
</ul>For information about the DMA adapter information that is provided by version 1 of the <b>DMA_ADAPTER_INFO_<i>XXX</i></b> structure, see <a href="..\wdm\ns-wdm-_dma_adapter_info_v1.md">DMA_ADAPTER_INFO_V1</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER_INFO</a>

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_DMA_ADAPTER_INFO callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>