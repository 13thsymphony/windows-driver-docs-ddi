---
UID: NF:storport.ScsiPortReadRegisterUchar
title: ScsiPortReadRegisterUchar macro
author: windows-driver-content
description: The ScsiPortReadRegisterUchar routine reads an unsigned byte value from the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportreadregisteruchar.htm
old-project: storage
ms.assetid: d5ea19e5-015d-451e-8e28-0b5a226f291a
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortReadRegisterUchar, ScsiPortReadRegisterUchar routine [Storage Devices], scsiprt_220f8972-dc09-4027-9cec-85a07ed5547d.xml, srb/ScsiPortReadRegisterUchar, storage.scsiportreadregisteruchar
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: storport.h
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
-	ScsiPortReadRegisterUchar
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# ScsiPortReadRegisterUchar function
The <b>ScsiPortReadRegisterUchar</b> routine reads an unsigned byte value from the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
void ScsiPortReadRegisterUchar(
   Register
);
```

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.


## Return Value

None

## Remarks

<b>ScsiPortReadRegisterUchar</b> ensures that the data is transferred correctly.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | storport.h (include Miniport.h, Scsi.h, Storport.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>