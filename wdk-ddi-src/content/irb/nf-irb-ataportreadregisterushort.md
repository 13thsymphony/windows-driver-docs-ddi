---
UID: NF:irb.AtaPortReadRegisterUshort
title: AtaPortReadRegisterUshort function
author: windows-driver-content
description: The AtaPortReadRegisterUshort routine reads a USHORT value from the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterushort.htm
old-project: storage
ms.assetid: a0a9792c-a2a1-4079-9e1c-c41c5b872fa0
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortReadRegisterUshort, AtaPortReadRegisterUshort routine [Storage Devices], atartns_4173b6fd-0784-4279-ae9e-d51469a000c6.xml, irb/AtaPortReadRegisterUshort, storage.ataportreadregisterushort
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
-	AtaPortReadRegisterUshort
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortReadRegisterUshort function
The <b>AtaPortReadRegisterUshort</b> routine reads a USHORT value from the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
USHORT AtaPortReadRegisterUshort(
  _In_ PUSHORT Register
);
````

## Parameters

`Register`

A pointer to the register to be read. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.


## Return Value

<b>AtaPortReadRegisterUshort</b> returns a USHORT value from the HBA's register.


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportreadregisteruchar.md">AtaPortReadRegisterUchar</a>



<a href="..\irb\nf-irb-ataportreadregisterulong.md">AtaPortReadRegisterUlong</a>