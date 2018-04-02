---
UID: NF:irb.AtaPortWritePortBufferUlong
title: AtaPortWritePortBufferUlong function
author: windows-driver-content
description: The AtaPortWritePortBufferUlong routine transfers the indicated number of ULONG values from a buffer to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportbufferulong.htm
old-project: storage
ms.assetid: 0ee4ef0a-1b6e-4e94-8a3d-ed5215dc5f31
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortWritePortBufferUlong, AtaPortWritePortBufferUlong routine [Storage Devices], atartns_877f49af-a38e-4468-896a-0e79a4e9effa.xml, irb/AtaPortWritePortBufferUlong, storage.ataportwriteportbufferulong
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
-	AtaPortWritePortBufferUlong
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortWritePortBufferUlong function
The <b>AtaPortWritePortBufferUlong</b> routine transfers the indicated number of ULONG values from a buffer to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
void AtaPortWritePortBufferUlong(
  PULONG Port,
  PULONG Buffer,
  ULONG  Count
);
```

## Parameters

`Port`

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.

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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550239">AtaPortWritePortBufferUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550249">AtaPortWritePortBufferUshort</a>