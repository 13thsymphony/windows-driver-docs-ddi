---
UID: NF:portcls.PcNewDmaChannel
title: PcNewDmaChannel function
author: windows-driver-content
description: The PcNewDmaChannel function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments.
old-location: audio\pcnewdmachannel.htm
old-project: audio
ms.assetid: 4a3a39ac-0db9-48a9-8da6-c2b914fa1de6
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: PcNewDmaChannel, PcNewDmaChannel function [Audio Devices], audio.pcnewdmachannel, audpc-routines_51deae73-e4dd-4b39-ae73-77cf31f8ec06.xml, portcls/PcNewDmaChannel
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: portcls.h
req.include-header: Portcls.h
req.target-type: Universal
req.target-min-winverclnt: Obsolete. For all new audio drivers, use a IPortWaveXxx::NewXxxDmaChannel method instead. The PortCls system driver implements the PcNewDmaChannel function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.
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
req.lib: Portcls.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Portcls.lib
-	Portcls.dll
api_name:
-	PcNewDmaChannel
product: Windows
targetos: Windows
req.typenames: PC_EXIT_LATENCY, *PPC_EXIT_LATENCY
---


# PcNewDmaChannel function
The <b>PcNewDmaChannel</b> function creates a new DMA-channel object. This function is obsolete; for more information, see the following comments.

## Syntax

````
NTSTATUS PcNewDmaChannel(
  _Out_    PDMACHANNEL         *OutDmaChannel,
  _In_opt_ PUNKNOWN            OuterUnknown,
  _In_     POOL_TYPE           PoolType,
  _In_     PDEVICE_DESCRIPTION DeviceDescription,
  _In_     PDEVICE_OBJECT      DeviceObject
);
````

## Parameters

`OutDmaChannel`

Output pointer for the DMA-channel object created by this function. This parameter points to a caller-allocated pointer variable into which the function outputs a reference to the newly created <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> object. Specify a valid, non-<b>NULL</b> pointer value for this parameter.

`OuterUnknown`

Pointer to the <a href="https://msdn.microsoft.com/33f1d79a-33fc-4ce5-a372-e08bda378332">IUnknown</a> interface of an object that needs to aggregate the object. Unless aggregation is required, set this parameter to <b>NULL</b>.

`PoolType`

Specifies the type of storage pool from which the object is to be allocated. This is a <a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a> enumeration value. Specify a nonpaged pool type for this parameter.

`DeviceDescription`

Pointer to a description of the physical device for which the caller is requesting a DMA object. This parameter points to a structure of type <a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>.

`DeviceObject`

Pointer to the device object for the physical adapter device. This parameter points to a system structure of type <a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>.


## Return Value

<b>PcNewDmaChannel</b> returns STATUS_SUCCESS if the call was successful. Otherwise, it returns an appropriate error code.

## Remarks

<b>PcNewDmaChannel</b> is obsolete. For all new audio drivers, use one of the following IPortWave <i>Xxx</i>::New<i>Xxx</i>DmaChannel methods in place of <b>PcNewDmaChannel</b>:


<a href="https://msdn.microsoft.com/library/windows/hardware/ff536916">IPortWavePci::NewMasterDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536900">IPortWaveCyclic::NewMasterDmaChannel</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536902">IPortWaveCyclic::NewSlaveDmaChannel</a>


For the sake of backward compatibility, the PortCls system driver will continue to support <b>PcNewDmaChannel</b>, and existing drivers can continue to use this function. For more information, see <a href="https://msdn.microsoft.com/0497acff-1e7f-45b9-b5ec-f1783ea7e900">DirectSound Hardware Acceleration in 64-Bit Versions of Windows XP</a>.

Specify the <i>PoolType</i> parameter to be one of the nonpaged pool types defined in the POOL_TYPE enumeration. The DMA-channel object must not reside in paged memory because several of the methods in the <a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a> interface can be called from IRQL DISPATCH_LEVEL.

The <i>OutDmaChannel</i> and <i>OuterUnknown </i>parameters follow the <a href="https://msdn.microsoft.com/e6b19110-37e2-4d23-a528-6393c12ab650">reference-counting conventions for COM objects</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Obsolete. For all new audio drivers, use a IPortWaveXxx::NewXxxDmaChannel method instead. The PortCls system driver implements the PcNewDmaChannel function in Microsoft Windows 98/Me and in Windows 2000 and later operating systems.  |
| **Target Platform** | Universal |
| **Header** | portcls.h (include Portcls.h) |
| **Library** | Portcls.lib |
| **IRQL** | PASSIVE_LEVEL |

## See Also

<a href="..\portcls\nn-portcls-idmachannel.md">IDmaChannel</a>



<a href="..\wdm\ns-wdm-_device_description.md">DEVICE_DESCRIPTION</a>



<a href="..\wudfwdm\ne-wudfwdm-_pool_type.md">POOL_TYPE</a>



<a href="..\wdm\ns-wdm-_device_object.md">DEVICE_OBJECT</a>