---
UID: NF:irb.AtaPortRequestTimer
title: AtaPortRequestTimer function
author: windows-driver-content
description: The AtaPortRequestTimer routine requests a timer callback.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportrequesttimer.htm
old-project: storage
ms.assetid: b057ae2e-53ae-4da9-8668-1ebca3c80998
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortRequestTimer, AtaPortRequestTimer routine [Storage Devices], atartns_604a8d41-c918-4121-97ef-10d3a7fbf3b4.xml, irb/AtaPortRequestTimer, storage.ataportrequesttimer
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
-	irb.h
api_name:
-	AtaPortRequestTimer
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortRequestTimer function
The <b>AtaPortRequestTimer</b> routine requests a timer callback.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
_IRQL_requires_same_ BOOLEAN AtaPortRequestTimer(
  PVOID      ChannelExtension,
  IDE_HW_DPC CallBackRoutine,
  ULONG      TimerValue
);
```

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`CallBackRoutine`

TBD

`TimerValue`

Time interval in units of microseconds.


## Return Value

None

## Remarks

The <b>AtaPortRequestTimer</b> routine informs the ATA port driver that it must call the timer routine that is pointed to by <i>TimerRoutine</i> in the number of microseconds indicated by <i>TimerValue</i>. 

The ATA port driver passes a pointer to the channel extension to the timer routine.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550234">AtaPortStallExecution</a>