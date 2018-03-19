---
UID: NF:irb.AtaPortReadPortUlong
title: AtaPortReadPortUlong function
author: windows-driver-content
description: The AtaPortReadPortUlong routine reads a ULONG value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadportulong.htm
old-project: storage
ms.assetid: f9e5fb0a-7add-462c-9b2a-2b543f7c7649
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortReadPortUlong, AtaPortReadPortUlong routine [Storage Devices], atartns_e2d91111-cf48-4987-82ff-055469d67dc8.xml, irb/AtaPortReadPortUlong, storage.ataportreadportulong
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
-	AtaPortReadPortUlong
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortReadPortUlong function
The <b>AtaPortReadPortUlong</b> routine reads a ULONG value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
ULONG AtaPortReadPortUlong(
  _In_ PULONG Port
);
````

## Parameters

`Port`

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


## Return Value

<b>AtaPortReadPortUlong</b> returns a ULONG value from the HBA's I/O port.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportreadportuchar.md">AtaPortReadPortUchar</a>



<a href="..\irb\nf-irb-ataportreadportushort.md">AtaPortReadPortUshort</a>