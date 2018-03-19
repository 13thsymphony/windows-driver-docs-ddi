---
UID: NF:srb.ScsiPortWriteRegisterUchar
title: ScsiPortWriteRegisterUchar function
author: windows-driver-content
description: The ScsiPortWriteRegisterUchar routine transfers a unsigned byte value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteregisteruchar.htm
old-project: storage
ms.assetid: 67764b34-3bd3-42ad-a1f8-765b4f11fcf6
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortWriteRegisterUchar, ScsiPortWriteRegisterUchar routine [Storage Devices], scsiprt_11b9d3b9-2866-4f07-a685-68d48e993748.xml, srb/ScsiPortWriteRegisterUchar, storage.scsiportwriteregisteruchar
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
-	ScsiPortWriteRegisterUchar
product: Windows
targetos: Windows
req.typenames: STOR_DEVICE_POWER_STATE, *PSTOR_DEVICE_POWER_STATE
req.product: Windows 10 or later.
---


# ScsiPortWriteRegisterUchar function
The <b>ScsiPortWriteRegisterUchar</b> routine transfers a unsigned byte value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID ScsiPortWriteRegisterUchar(
  _In_ PUCHAR Register,
  _In_ UCHAR  Value
);
````

## Parameters

`Register`

Pointer to the register. The given <i>Register</i> must be in a mapped memory-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Value`

Specifies the value to be written to the HBA's register.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | srb.h (include Miniport.h, Scsi.h, Storport.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>