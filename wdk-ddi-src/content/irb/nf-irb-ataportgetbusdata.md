---
UID : NF:irb.AtaPortGetBusData
title : AtaPortGetBusData function
author : windows-driver-content
description : The AtaPortGetBusData routine retrieves data from the location that is specified by ConfigDataOffset within the device's PCI configuration space.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location : storage\ataportgetbusdata.htm
old-project : storage
ms.assetid : bfff10ab-7e15-4db3-b808-947d61844bc0
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : AtaPortGetBusData, storage.ataportgetbusdata, AtaPortGetBusData routine [Storage Devices], irb/AtaPortGetBusData, atartns_a137d697-85fa-4d99-964f-94e9bcbb6b7b.xml
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : irb.h
req.include-header : Ata.h, Irb.h
req.target-type : Desktop
req.target-min-winverclnt : 
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
req.lib : Pciidex.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : IDE_POWER_STATE
---


# AtaPortGetBusData function
The <b>AtaPortGetBusData</b> routine retrieves data from the location that is specified by <i>ConfigDataOffset</i> within the device's PCI configuration space.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
ULONG AtaPortGetBusData(
  _In_ PVOID ControllerExtension,
  _In_ PVOID Buffer,
  _In_ ULONG ConfigDataOffset,
  _In_ ULONG BufferLength
);
````

## Parameters

`ControllerExtension`

A pointer to the HBA controller extension.

`Buffer`

A pointer to the buffer where the retrieved data is returned.

`ConfigDataOffset`

Specifies an offset into the device's PCI bus configuration space where the return value is found.

`BufferLength`

Specifies the length, in bytes, of the buffer.


## Return Value

<b>AtaPortGetBusData</b> returns the amount of the retrieved data in bytes.

## Remarks

<b>AtaPortGetBusData</b> retrieves data from the specified offset in the device's PCI bus configuration space and returns it in the buffer that is provided.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<a href="..\irb\nf-irb-ataportsetbusdata.md">AtaPortSetBusData</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortGetBusData routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>