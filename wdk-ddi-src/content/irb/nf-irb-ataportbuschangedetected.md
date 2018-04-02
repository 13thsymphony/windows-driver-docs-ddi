---
UID: NF:irb.AtaPortBusChangeDetected
title: AtaPortBusChangeDetected function
author: windows-driver-content
description: The AtaPortBusChangeDetected routine notifies the port driver of changes in the device configuration on the indicated channel.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportbuschangedetected.htm
old-project: storage
ms.assetid: e5a3d4dc-7446-49c1-985a-9d3a9d43dc15
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortBusChangeDetected, AtaPortBusChangeDetected routine [Storage Devices], irb/AtaPortBusChangeDetected, storage.ataportbuschangedetected
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
-	AtaPortBusChangeDetected
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortBusChangeDetected function
The <b>AtaPortBusChangeDetected</b> routine notifies the port driver of changes in the device configuration on the indicated channel.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
void AtaPortBusChangeDetected(
  PVOID ChannelExtension
);
```

## Parameters

`ChannelExtension`

A pointer to the channel extension.


## Return Value

None

## Remarks

The miniport driver uses this routine to report the arrival or removal of any device that is attached to the channel. In response, the port driver will initiate a re-scan to discover and initialize the device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |