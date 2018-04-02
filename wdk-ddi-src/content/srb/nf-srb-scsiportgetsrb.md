---
UID: NF:srb.ScsiPortGetSrb
title: ScsiPortGetSrb function
author: windows-driver-content
description: The ScsiPortGetSrb routine returns a pointer to an active SCSI request for a particular logical unit.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportgetsrb.htm
old-project: storage
ms.assetid: c8f0e47c-4d06-445f-a6dd-9bd80fc490bc
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortGetSrb, ScsiPortGetSrb routine [Storage Devices], scsiprt_28205a6f-8758-4aed-8fae-94a12c216cf4.xml, srb/ScsiPortGetSrb, storage.scsiportgetsrb
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
-	ScsiPortGetSrb
product:
- Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortGetSrb function
The <b>ScsiPortGetSrb</b> routine returns a pointer to an active SCSI request for a particular logical unit.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
SCSIPORT_API PSCSI_REQUEST_BLOCK ScsiPortGetSrb(
  PVOID DeviceExtension,
  UCHAR PathId,
  UCHAR TargetId,
  UCHAR Lun,
  LONG  QueueTag
);
```

## Parameters

`DeviceExtension`

Pointer to the miniport driver's per-HBA storage area.

`PathId`

Identifies the SCSI bus.

`TargetId`

Identifies the target controller or device on the bus.

`Lun`

Identifies the logical unit number of the target device.

`QueueTag`

Specifies the queue tag if the miniport driver handles tagged requests; SP_UNTAGGED indicates that the request is not tagged.


## Return Value

<b>ScsiPortGetSrb</b> returns a pointer to a request for the specified logical unit. If there is no outstanding request for the given peripheral or if the <i>QueueTag</i> value is invalid, it returns <b>NULL</b>.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff565393">SCSI_REQUEST_BLOCK</a>