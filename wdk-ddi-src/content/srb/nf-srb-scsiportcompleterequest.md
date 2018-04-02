---
UID: NF:srb.ScsiPortCompleteRequest
title: ScsiPortCompleteRequest function
author: windows-driver-content
description: The ScsiPortCompleteRequest routine completes all of the active requests for the given SCSI bus, controller, or LU, including a request being processed by the calling miniport driver routine.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the Storport driver and Storport miniport driver models.
old-location: storage\scsiportcompleterequest.htm
old-project: storage
ms.assetid: 9cd17a86-6652-414d-a80d-2e61c0ac99b6
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortCompleteRequest, ScsiPortCompleteRequest routine [Storage Devices], scsiprt_be6690c0-6cfa-4a71-9877-176ed2c742e8.xml, srb/ScsiPortCompleteRequest, storage.scsiportcompleterequest
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
-	ScsiPortCompleteRequest
product:
- Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortCompleteRequest function
The <b>ScsiPortCompleteRequest</b> routine completes all of the active requests for the given SCSI bus, controller, or LU, including a request being processed by the calling miniport driver routine.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
SCSIPORT_API VOID ScsiPortCompleteRequest(
  PVOID HwDeviceExtension,
  UCHAR PathId,
  UCHAR TargetId,
  UCHAR Lun,
  UCHAR SrbStatus
);
```

## Parameters

`HwDeviceExtension`

Pointer to the hardware device extension. This is a per-HBA storage area that the port driver allocates and initializes on behalf of the miniport driver. Miniport drivers usually store HBA-specific information in this extension, such as the state of the HBA and the HBA's mapped access ranges. This area is available to the miniport driver in the <b>DeviceExtension-&gt;HwDeviceExtension</b> member of the HBA's device object immediately after the miniport driver calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff564645">ScsiPortInitialize</a>. The port driver frees this memory when it removes the device.

`PathId`

Identifies the SCSI bus; SP_UNTAGGED indicates all buses controlled by the HBA.

`TargetId`

Identifies the target controller or device on the given buses; SP_UNTAGGED indicates all targets on the bus.

`Lun`

Identifies the logical unit for the given target controller or device; SP_UNTAGGED indicates all logical units for the given target controllers on the given buses.

`SrbStatus`

Specifies the completion status to be set in the <b>SrbStatus </b>member of each SRB.


## Return Value

None

## Remarks

<b>ScsiPortCompleteRequest</b> can be called to complete outstanding requests after a bus reset, a device reset, or an abort, rather than calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a> for each outstanding request individually. After calling <b>ScsiPortCompleteRequest</b>, do not also call <b>ScsiPortNotification</b>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564657">ScsiPortNotification</a>