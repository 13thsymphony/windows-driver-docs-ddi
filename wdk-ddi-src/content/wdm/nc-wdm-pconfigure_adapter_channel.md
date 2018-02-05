---
UID : NC:wdm.PCONFIGURE_ADAPTER_CHANNEL
title : PCONFIGURE_ADAPTER_CHANNEL
author : windows-driver-content
description : The ConfigureAdapterChannel routine invokes a custom function that is implemented by the DMA controller represented by an adapter object.
old-location : kernel\configureadapterchannel.htm
old-project : kernel
ms.assetid : 964B305F-5B9E-4705-89BA-DBAE43464FB1
ms.author : windowsdriverdev
ms.date : 1/4/2018
ms.keywords : kernel.configureadapterchannel, ConfigureAdapterChannel, ConfigureAdapterChannel callback function [Kernel-Mode Driver Architecture], ConfigureAdapterChannel, PCONFIGURE_ADAPTER_CHANNEL, PCONFIGURE_ADAPTER_CHANNEL, wdm/ConfigureAdapterChannel
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : callback
req.header : wdm.h
req.include-header : Wdm.h, Ntddk.h, Ntifs.h
req.target-type : Desktop
req.target-min-winverclnt : Available starting with Windows 8.
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : "<= DISPATCH_LEVEL"
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
req.product : Windows 10 or later.
---


# PCONFIGURE_ADAPTER_CHANNEL callback function
The <b>ConfigureAdapterChannel</b> routine invokes a custom function that is implemented by the DMA controller represented by an adapter object.

## Syntax

```
PCONFIGURE_ADAPTER_CHANNEL PconfigureAdapterChannel;

NTSTATUS PconfigureAdapterChannel(
  PDMA_ADAPTER DmaAdapter,
  ULONG FunctionNumber,
  PVOID Context
)
{...}
```

## Parameters

`DmaAdapter`

A pointer to a <a href="..\wdm\ns-wdm-_dma_adapter.md">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel. The caller obtained this pointer from a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> routine.

`FunctionNumber`

The number of the custom function to select. For more information, see the Remarks section.

`Context`

A pointer to the configuration parameters for the custom function that is specified by <i>FunctionNumber</i>. The function is implemented by the DMA controller and can be accessed by a device driver through the adapter object. The DMA controller and the device driver must agree on the meaning of these configuration parameters. The data that <i>Context</i> points to is opaque to the operating system.


## Return Value

<b>ConfigureAdapterChannel</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.
<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_NOT_IMPLEMENTED</dt>
</dl>
</td>
<td width="60%">
The  DMA extension does not implement the function specified by <i>FunctionNumber</i>.

</td>
</tr>
</table>

## Remarks

<b>ConfigureAdapterChannel</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>ConfigureAdapterChannel</b> only for system DMA adapters. Do not use this routine for a bus-master adapter.
    

A particular system DMA controller might have special hardware features that device drivers can access through a set of one or more custom functions. A controller might implement more than one custom function, in which case each function is identified by a different function number. These functions abstract the DMA hardware features so that the same functions can be supported on different hardware platforms.

Typically, a custom function sets state information in the DMA controller to configure hardware features for use  in subsequent DMA transfers.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Available starting with Windows 8. Available starting with Windows 8. |
| **Target Platform** | Desktop |
| **Header** | wdm.h (include Wdm.h, Ntddk.h, Ntifs.h) |
| **IRQL** | "<= DISPATCH_LEVEL" |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff549220">IoGetDmaAdapter</a>

<a href="..\wdm\ns-wdm-_dma_operations.md">DMA_OPERATIONS</a>

<a href="..\wdm\ns-wdm-_dma_adapter_info.md">DMA_ADAPTER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCONFIGURE_ADAPTER_CHANNEL callback function%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>