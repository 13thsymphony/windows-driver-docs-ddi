---
UID: NF:storport.ScsiPortWritePortUshort
title: ScsiPortWritePortUshort macro
author: windows-driver-content
description: The ScsiPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportushort.htm
old-project: storage
ms.assetid: 4b1accd8-5dbe-47d6-822e-1997a6ab5082
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: ScsiPortWritePortUshort, ScsiPortWritePortUshort routine [Storage Devices], scsiprt_e7e27190-3f51-4ede-9b4d-fcc437f46d17.xml, srb/ScsiPortWritePortUshort, storage.scsiportwriteportushort
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
-	ScsiPortWritePortUshort
product:
- Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# ScsiPortWritePortUshort function
The <b>ScsiPortWritePortUshort</b> routine transfers a USHORT value to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
void ScsiPortWritePortUshort(
   Port,
   Value
);
```

## Parameters

`Port`

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Value`

Specifies the value to be written to the HBA's I/O port.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | storport.h (include Miniport.h, Scsi.h, Storport.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff564629">ScsiPortGetDeviceBase</a>