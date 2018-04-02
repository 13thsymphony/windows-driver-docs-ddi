---
UID: NF:srb.ScsiPortWriteRegisterBufferUshort
title: ScsiPortWriteRegisterBufferUshort function
author: windows-driver-content
description: The ScsiPortWriteRegisterBufferUshort routine transfers a given number of USHORT values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisterbufferushort.htm
old-project: storage
ms.assetid: 663c0543-7059-4fb7-be3d-57edbba6bf83
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortWriteRegisterBufferUshort, ScsiPortWriteRegisterBufferUshort routine [Storage Devices], scsiprt_300e2355-e8b2-4341-912d-a24954568824.xml, srb/ScsiPortWriteRegisterBufferUshort, storage.scsiportwriteregisterbufferushort
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
-	ScsiPortWriteRegisterBufferUshort
product:
- Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortWriteRegisterBufferUshort function
The <b>ScsiPortWriteRegisterBufferUshort</b> routine transfers a given number of USHORT values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
SCSIPORT_API VOID ScsiPortWriteRegisterBufferUshort(
  PUSHORT Register,
  PUSHORT Buffer,
  ULONG   Count
);
```

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Buffer`

Pointer to a buffer containing the data to be written.

`Count`

Specifies the number of USHORT values to be transferred to the HBA.


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