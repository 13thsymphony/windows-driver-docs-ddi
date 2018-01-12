---
UID: NF:portcls.IPortWavePci.NewMasterDmaChannel
title: IPortWavePci::NewMasterDmaChannel method
author: windows-driver-content
description: The NewMasterDmaChannel method creates a new instance of a bus-master DMA channel.
old-location: audio\iportwavepci_newmasterdmachannel.htm
old-project: audio
ms.assetid: a4128541-1982-413d-a013-422ca1cf4542
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: IPortWavePci, IPortWavePci::NewMasterDmaChannel, NewMasterDmaChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: method
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: IPortWavePci.NewMasterDmaChannel
req.alt-loc: portcls.h
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
req.typenames: *PPC_EXIT_LATENCY, PC_EXIT_LATENCY
---

# IPortWavePci::NewMasterDmaChannel method



## -description
The <code>NewMasterDmaChannel</code> method creates a new instance of a bus-master DMA channel.



## -syntax

````
NTSTATUS NewMasterDmaChannel(
  [out]          PDMACHANNEL   *DmaChannel,
  [in, optional] PUNKNOWN      OuterUnknown,
  [in]           POOL_TYPE     PoolType,
  [in, optional] PRESOURCELIST ResourceList,
  [in]           BOOLEAN       ScatterGather,
  [in]           BOOLEAN       Dma32BitAddresses,
  [in]           BOOLEAN       Dma64BitAddresses,
  [in]           BOOLEAN       IgnoreCount,
  [in]           DMA_WIDTH     DmaWidth,
  [in]           DMA_SPEED     DmaSpeed,
  [in]           ULONG         MaximumLength,
  [in]           ULONG         DmaPort
);
````


## -parameters

### -param DmaChannel [out]

Output pointer for the DMA channel. This parameter points to a caller-allocated pointer variable into which the method writes a pointer to the new DMA-channel object's <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> interface.


### -param OuterUnknown [in, optional]

Pointer to the <b>IUnknown</b> interface of an object that needs to aggregate the DMA-channel object. This parameter is optional. If aggregation is not required, specify this parameter as <b>NULL</b>.


### -param PoolType [in]

Specifies the type of storage pool from which the object is to be allocated. This is a <a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a> enumeration value. Specify a nonpaged pool type for this parameter.


### -param ResourceList [in, optional]

Pointer to the miniport driver's resource list, which is an <a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a> object. This parameter is optional and can be specified as <b>NULL</b>. The <code>NewMasterDmaChannel</code> method currently makes no use of this parameter.


### -param ScatterGather [in]

Requests that the DMA channel support scatter/gather DMA. Always set this parameter to <b>TRUE</b>.


### -param Dma32BitAddresses [in]

Specifies the use of 32-bit addresses for DMA operations.


### -param Dma64BitAddresses [in]

Specifies the use of 64-bit addresses for DMA operations.


### -param IgnoreCount [in]

Indicates whether to ignore the DMA controller's transfer counter. Set to <b>TRUE</b> if the DMA controller in this platform does not maintain an accurate transfer counter, and therefore requires a workaround.


### -param DmaWidth [in]

Not used. Set to (DMA_WIDTH)(-1).


### -param DmaSpeed [in]

Not used. Set to (DMA_SPEED)(-1).


### -param MaximumLength [in]

Maximum number of bytes in the buffer that will be associated with this DMA channel.


### -param DmaPort [in]

Not used. Set to 0.


## -returns
<code>NewMasterDmaChannel</code> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.


## -remarks
The definitions of the call parameters for the <code>NewMasterDmaChannel</code> method are similar to those for the members of the <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a> structure with the same names.

Specify the <i>PoolType</i> parameter to be one of the nonpaged pool types defined in the POOL_TYPE enumeration. The DMA-channel object must not reside in paged memory because several of the methods in the <b>IDmaChannel</b> interface can be called from IRQL DISPATCH_LEVEL.

The <i>DmaChannel</i>, <i>OuterUnknown</i>, and <i>ResourceList</i> parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt><a href="http://go.microsoft.com/fwlink/p/?linkid=531356" target="_blank">Universal</a></dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Portcls.h (include Portcls.h)</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
IRQL

</th>
<td width="70%">
PASSIVE_LEVEL

</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="https://msdn.microsoft.com/library/windows/hardware/ff536905">IPortWavePci</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>
</dt>
<dt>
<a href="..\portcls\nn-portcls-iresourcelist.md">IResourceList</a>
</dt>
<dt>
<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>
</dt>
<dt>
<a href="..\wdm\ne-wdm-_pool_type.md">POOL_TYPE</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [audio\audio]:%20IPortWavePci::NewMasterDmaChannel method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

