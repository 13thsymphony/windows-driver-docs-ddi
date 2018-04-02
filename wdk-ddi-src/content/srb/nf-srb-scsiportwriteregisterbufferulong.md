---
UID: NF:srb.ScsiPortWriteRegisterBufferUlong
title: ScsiPortWriteRegisterBufferUlong function
author: windows-driver-content
description: The ScsiPortWriteRegisterBufferUlong routine transfers a given number of ULONG values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisterbufferulong.htm
old-project: storage
ms.assetid: d77b188e-45b2-47c3-bee5-557886925d3f
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortWriteRegisterBufferUlong, ScsiPortWriteRegisterBufferUlong routine [Storage Devices], scsiprt_f6ce8fd2-0d06-4bda-9673-983af38f08e9.xml, srb/ScsiPortWriteRegisterBufferUlong, storage.scsiportwriteregisterbufferulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: srb.h
req.include-header: Miniport.h, Scsi.h, Storport.h
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
-	ScsiPortWriteRegisterBufferUlong
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortWriteRegisterBufferUlong function
The <b>ScsiPortWriteRegisterBufferUlong</b> routine transfers a given number of ULONG values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
SCSIPORT_API VOID ScsiPortWriteRegisterBufferUlong(
  PULONG Register,
  PULONG Buffer,
  ULONG  Count
);
```

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Buffer`

Pointer to a buffer containing the data to be written.

`Count`

Specifies the number of ULONG values to be transferred to the HBA.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h, Storport.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>