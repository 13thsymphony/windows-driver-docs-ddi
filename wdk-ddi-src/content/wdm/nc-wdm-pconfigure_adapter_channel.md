---
UID: NC.wdm.PCONFIGURE_ADAPTER_CHANNEL
title: PCONFIGURE_ADAPTER_CHANNEL
author: windows-driver-content
description: The ConfigureAdapterChannel routine invokes a custom function that is implemented by the DMA controller represented by an adapter object.
old-location: kernel\configureadapterchannel.htm
old-project: kernel
ms.assetid: 964B305F-5B9E-4705-89BA-DBAE43464FB1
ms.author: windowsdriverdev
ms.date: 12/7/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
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
req.alt-api: ConfigureAdapterChannel
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
req.irql: <= DISPATCH_LEVEL
req.product: Windows 10 or later.
---

# PCONFIGURE_ADAPTER_CHANNEL callback



## -description
The <b>ConfigureAdapterChannel</b> routine invokes a custom function that is implemented by the DMA controller represented by an adapter object.



## -prototype

````
PCONFIGURE_ADAPTER_CHANNEL ConfigureAdapterChannel;

NTSTATUS ConfigureAdapterChannel(
  _In_ PDMA_ADAPTER DmaAdapter,
  _In_ ULONG        FunctionNumber,
  _In_ PVOID        Context
)
{ ... }
````


## -parameters

### -param DmaAdapter [in]

A pointer to a <a href="kernel.dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel. The caller obtained this pointer from a previous call to the <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param FunctionNumber [in]

The number of the custom function to select. For more information, see the Remarks section.


### -param Context [in]

A pointer to the configuration parameters for the custom function that is specified by <i>FunctionNumber</i>. The function is implemented by the DMA controller and can be accessed by a device driver through the adapter object. The DMA controller and the device driver must agree on the meaning of these configuration parameters. The data that <i>Context</i> points to is opaque to the operating system.


## -returns
<b>ConfigureAdapterChannel</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.
<dl>
<dt>STATUS_NOT_IMPLEMENTED</dt>
</dl>The  DMA extension does not implement the function specified by <i>FunctionNumber</i>.

 


## -remarks
<b>ConfigureAdapterChannel</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="kernel.dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

Use <b>ConfigureAdapterChannel</b> only for system DMA adapters. Do not use this routine for a bus-master adapter.
    

A particular system DMA controller might have special hardware features that device drivers can access through a set of one or more custom functions. A controller might implement more than one custom function, in which case each function is identified by a different function number. These functions abstract the DMA hardware features so that the same functions can be supported on different hardware platforms.

Typically, a custom function sets state information in the DMA controller to configure hardware features for use  in subsequent DMA transfers.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Version

</th>
<td width="70%">
Available starting with Windows 8.

</td>
</tr>
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
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
&lt;= DISPATCH_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="kernel.dma_adapter_info">DMA_ADAPTER</a>
</dt>
<dt>
<a href="kernel.dma_operations">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PCONFIGURE_ADAPTER_CHANNEL callback function%20 RELEASE:%20(12/7/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

