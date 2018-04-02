---
UID: NF:srb.ScsiPortFreeDeviceBase
title: ScsiPortFreeDeviceBase function
author: windows-driver-content
description: The ScsiPortFreeDeviceBase routine frees a range of device I/O or memory space addresses previously mapped into the system address space with ScsiPortGetDeviceBase.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportfreedevicebase.htm
old-project: storage
ms.assetid: 391f3b20-175f-4b27-b30f-34ccc43ca650
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortFreeDeviceBase, ScsiPortFreeDeviceBase routine [Storage Devices], scsiprt_e74eafd2-bedf-46d2-b71a-fb36b6bba128.xml, srb/ScsiPortFreeDeviceBase, storage.scsiportfreedevicebase
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h
req.target-type: Desktop
req.target-min-winverclnt: 
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
req.lib: Scsiport.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Scsiport.lib
-	Scsiport.dll
api_name:
-	ScsiPortFreeDeviceBase
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortFreeDeviceBase function
The <b>ScsiPortFreeDeviceBase</b> routine frees a range of device I/O or memory space addresses previously mapped into the system address space with <b>ScsiPortGetDeviceBase</b>.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
SCSIPORT_API VOID ScsiPortFreeDeviceBase(
  PVOID HwDeviceExtension,
  PVOID MappedAddress
);
```

## Parameters

`HwDeviceExtension`

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564645">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device.

`MappedAddress`

Pointer to the base address of the range to be freed. This address must be the same as that returned by <a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>.


## Return Value

None

## Remarks

If a miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine determines that the driver does not need a particular mapped base address for an adapter, it must release the mapping by calling this routine. For example, when a miniport driver determines there are no supported HBAs on a particular I/O bus, it must call <b>ScsiPortFreeDeviceBase</b> with each mapped address returned by <b>ScsiPortGetDeviceBase</b>, if any calls to this routine were made.

<b>ScsiPortFreeDeviceBase</b> can be called only from miniport driver's <a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a> routine. Calls from other miniport driver routines will result in system failure or incorrect operation for the caller.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557300">HwScsiFindAdapter</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>