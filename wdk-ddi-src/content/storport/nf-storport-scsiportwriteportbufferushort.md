---
UID: NF:storport.ScsiPortWritePortBufferUshort
title: ScsiPortWritePortBufferUshort macro
author: windows-driver-content
description: The ScsiPortWritePortBufferUshort routine transfers a given number of USHORT values from a buffer to the HBA.Note  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future.
old-location: storage\scsiportwriteportbufferushort.htm
old-project: storage
ms.assetid: ca6bd14b-533d-4451-b54f-29bc566c968d
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: ScsiPortWritePortBufferUshort, ScsiPortWritePortBufferUshort routine [Storage Devices], scsiprt_b04295df-d370-4015-a705-71652d4ab4f7.xml, srb/ScsiPortWritePortBufferUshort, storage.scsiportwriteportbufferushort
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
-	ScsiPortWritePortBufferUshort
product: Windows
targetos: Windows
req.typenames: STOR_SPINLOCK
req.product: Windows 10 or later.
---


# ScsiPortWritePortBufferUshort function
The <b>ScsiPortWritePortBufferUshort</b> routine transfers a given number of USHORT values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID ScsiPortWritePortBufferUshort(
  _In_ PUSHORT Port,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````

## Parameters

`Port`

Pointer to the I/O port. The given <i>Port</i> must be in a mapped I/O-space range returned by <b>ScsiPortGetDeviceBase</b>.

`Buffer`

Pointer to the buffer.

`Count`

Specifies the number of USHORT values to be written to the HBA.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | storport.h (include Miniport.h, Scsi.h, Storport.h) |
| **Library** | Scsiport.lib |

## See Also

<a href="..\srb\nf-srb-scsiportgetdevicebase.md">ScsiPortGetDeviceBase</a>