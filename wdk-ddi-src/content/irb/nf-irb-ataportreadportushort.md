---
UID: NF:irb.AtaPortReadPortUshort
title: AtaPortReadPortUshort function
author: windows-driver-content
description: The AtaPortReadPortUshort routine reads a USHORT value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportushort.htm
old-project: storage
ms.assetid: e2534e79-293e-41db-b874-3f39aa5af864
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortReadPortUshort, AtaPortReadPortUshort routine [Storage Devices], atartns_935ac51b-c226-48d2-acf0-ae1cfe5bfd60.xml, irb/AtaPortReadPortUshort, storage.ataportreadportushort
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
-	AtaPortReadPortUshort
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortReadPortUshort function
The <b>AtaPortReadPortUshort</b> routine reads a USHORT value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
USHORT AtaPortReadPortUshort(
  PUSHORT Port
);
```

## Parameters

`Port`

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>.


## Return Value

<b>AtaPortReadPortUshort</b> returns a USHORT value from the HBA's I/O port.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550160">AtaPortGetDeviceBase</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550182">AtaPortReadPortUchar</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550184">AtaPortReadPortUlong</a>