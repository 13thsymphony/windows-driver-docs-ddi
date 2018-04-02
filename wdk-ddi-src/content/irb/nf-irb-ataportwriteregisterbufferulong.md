---
UID: NF:irb.AtaPortWriteRegisterBufferUlong
title: AtaPortWriteRegisterBufferUlong function
author: windows-driver-content
description: The AtaPortWriteRegisterBufferUlong routine transfers the indicated number of ULONG values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteregisterbufferulong.htm
old-project: storage
ms.assetid: 95f1e2c2-2b70-4a98-b075-e582b6a56e9d
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortWriteRegisterBufferUlong, AtaPortWriteRegisterBufferUlong routine [Storage Devices], atartns_678d25ba-ba41-4a94-b689-5f19a89ace7f.xml, irb/AtaPortWriteRegisterBufferUlong, storage.ataportwriteregisterbufferulong
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: irb.h
req.include-header: Ata.h, Irb.h
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
req.lib: Ataport.lib; Pciidex.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
api_name:
-	AtaPortWriteRegisterBufferUlong
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortWriteRegisterBufferUlong function
The <b>AtaPortWriteRegisterBufferUlong</b> routine transfers the indicated number of ULONG values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
void AtaPortWriteRegisterBufferUlong(
  PULONG Register,
  PULONG Buffer,
  ULONG  Count
);
```

## Parameters

`Register`

Contains the destination register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses at are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.

`Buffer`

A pointer to the source buffer.

`Count`

Specifies the number of ULONG values to write to the HBA.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550264">AtaPortWriteRegisterBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550273">AtaPortWriteRegisterBufferUshort</a>