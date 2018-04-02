---
UID: NF:irb.AtaPortReadRegisterBufferUchar
title: AtaPortReadRegisterBufferUchar function
author: windows-driver-content
description: The AtaPortReadRegisterBufferUchar routine transfers a specified number of unsigned bytes from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterbufferuchar.htm
old-project: storage
ms.assetid: adc6724b-f3dc-4605-8ee1-198c88bc3fcd
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortReadRegisterBufferUchar, AtaPortReadRegisterBufferUchar routine [Storage Devices], atartns_5c57e652-3b37-4673-b5cf-fbcdf38853ad.xml, irb/AtaPortReadRegisterBufferUchar, storage.ataportreadregisterbufferuchar
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
-	AtaPortReadRegisterBufferUchar
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortReadRegisterBufferUchar function
The <b>AtaPortReadRegisterBufferUchar</b> routine transfers a specified number of unsigned bytes from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
void AtaPortReadRegisterBufferUchar(
  PUCHAR Register,
  PUCHAR Buffer,
  ULONG  Count
);
```

## Parameters

`Register`

Contains the register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.

`Buffer`

A pointer to the destination buffer.

`Count`

Specifies the number of bytes to read from the HBA.


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



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550190">AtaPortReadRegisterBufferUlong</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550192">AtaPortReadRegisterBufferUshort</a>