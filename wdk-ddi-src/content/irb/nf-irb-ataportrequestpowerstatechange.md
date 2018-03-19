---
UID: NF:irb.AtaPortRequestPowerStateChange
title: AtaPortRequestPowerStateChange function
author: windows-driver-content
description: The AtaPortRequestPowerStateChange routine requests a power state transition for the indicated device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequestpowerstatechange.htm
old-project: storage
ms.assetid: 37cf1552-2cbe-4b80-b220-cfa853674e1b
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortRequestPowerStateChange, AtaPortRequestPowerStateChange routine [Storage Devices], irb/AtaPortRequestPowerStateChange, storage.ataportrequestpowerstatechange
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Irb.h
api_name:
-	AtaPortRequestPowerStateChange
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortRequestPowerStateChange function
The <b>AtaPortRequestPowerStateChange</b> routine requests a power state transition for the indicated device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID AtaPortRequestPowerStateChange(
   IN PVOID           ChannelExtension,
   IN UCHAR           TargetId,
   IN UCHAR           Lun,
   IN IDE_POWER_STATE DesiredPowerState
);
````

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`TargetId`

Specifies the target identifier of the device.

`Lun`

Specifies the logical unit number (LUN).

`DesiredPowerState`

Contains an enumerator value of type <a href="..\irb\ne-irb-ide_power_state.md">IDE_POWER_STATE</a> that indicates the power state to which the indicated device should be changed.


## Return Value

None

## Remarks

The <b>AtaPortRequestPowerStateChange</b> routine is used when a miniport driver might have to initiate a power state change, such as when a hot-plug operation occurs. 

<div class="alert"><b>Note</b>   The practice of doing idle detection from an ATA miniport driver is discouraged. </div>
<div> </div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |

## See Also

<a href="..\irb\ne-irb-ide_power_state.md">IDE_POWER_STATE</a>