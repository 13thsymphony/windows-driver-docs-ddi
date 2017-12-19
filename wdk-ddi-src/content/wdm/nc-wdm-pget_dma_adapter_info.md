---
UID: NC.wdm.PGET_DMA_ADAPTER_INFO
title: PGET_DMA_ADAPTER_INFO
author: windows-driver-content
description: The GetDmaAdapterInfo routine retrieves information about the hardware capabilities of a system DMA channel.
old-location: kernel\getdmaadapterinfo.htm
old-project: kernel
ms.assetid: 2F502ACA-0CFF-46A1-B54C-1034D6E56815
ms.author: windowsdriverdev
ms.date: 12/15/2017
ms.keywords: _WDI_TYPE_PMK_NAME, WDI_TYPE_PMK_NAME, PWDI_TYPE_PMK_NAME, *PWDI_TYPE_PMK_NAME
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
req.alt-api: GetDmaAdapterInfo
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

# PGET_DMA_ADAPTER_INFO callback



## -description
The <b>GetDmaAdapterInfo</b> routine retrieves information about the hardware capabilities of a system DMA channel.



## -prototype

````
PGET_DMA_ADAPTER_INFO GetDmaAdapterInfo;

NTSTATUS GetDmaAdapterInfo(
  _In_    PDMA_ADAPTER       DmaAdapter,
  _Inout_ PDMA_ADAPTER_INFO  AdapterInfo
)
{ ... }
````


## -parameters

### -param  DmaAdapter [in]

A pointer to a <a href="kernel.dma_adapter">DMA_ADAPTER</a> structure. This structure is the adapter object that represents the driver's system DMA channel. The caller obtained this pointer from a previous call to the <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> routine.


### -param  AdapterInfo [in, out]

A pointer to a caller-allocated <a href="kernel.dma_adapter_info">DMA_ADAPTER_INFO</a> structure. The routine writes information about the system DMA controller into this structure. The caller must set the
        <b>Version</b> member of this structure to DMA_ADAPTER_INFO_VERSION1 before calling <b>GetDmaAdapterInfo</b>.


## -returns
<b>GetDmaAdapterInfo</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>The routine does not support the specified version of the <b>DMA_ADAPTER_INFO_<i>XXX</i></b> structure.

 


## -remarks
<b>GetDmaAdapterInfo</b><i> is not a system routine that can be called directly by name. This routine can be called only by pointer from the address returned in a </i><a href="kernel.dma_operations">DMA_OPERATIONS</a><i> structure. </i>Drivers obtain the address of this routine by calling <a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a> with the <b>Version</b> member of the <i>DeviceDescription</i> parameter set to DEVICE_DESCRIPTION_VERSION3. If <b>IoGetDmaAdapter</b> returns <b>NULL</b>, the routine is not available on your platform.

<b>GetDmaAdapterInfo</b> retrieves the following information:

The maximum number of elements in a scatter/gather list that the DMA controller can process in a single scatter/gather DMA operation.

The width, in bits, of a DMA address.

For information about the DMA adapter information that is provided by version 1 of the <b>DMA_ADAPTER_INFO_<i>XXX</i></b> structure, see <a href="kernel.dma_adapter_info_v1">DMA_ADAPTER_INFO_V1</a>.


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
<a href="kernel.dma_adapter">DMA_ADAPTER</a>
</dt>
<dt>
<a href="kernel.dma_adapter_info">DMA_ADAPTER_INFO</a>
</dt>
<dt>
<a href="kernel.dma_operations">DMA_OPERATIONS</a>
</dt>
<dt>
<a href="kernel.iogetdmaadapter">IoGetDmaAdapter</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PGET_DMA_ADAPTER_INFO callback function%20 RELEASE:%20(12/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

