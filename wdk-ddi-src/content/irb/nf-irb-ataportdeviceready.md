---
UID: NF:irb.AtaPortDeviceReady
title: AtaPortDeviceReady function
author: windows-driver-content
description: The AtaPortDeviceReady routine informs the port driver that the indicated device is ready to accept new requests.
old-location: storage\ataportdeviceready.htm
old-project: storage
ms.assetid: 65cbed1a-35f9-44f7-941a-ffc87cc79649
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortDeviceReady, AtaPortDeviceReady routine [Storage Devices], atartns_28cebf8c-cdda-46f4-9785-184552630769.xml, irb/AtaPortDeviceReady, storage.ataportdeviceready
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
-	AtaPortDeviceReady
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortDeviceReady function
The <b>AtaPortDeviceReady</b> routine informs the port driver that the indicated device is ready to accept new requests. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
void AtaPortDeviceReady(
  PVOID ChannelExtension,
  UCHAR TargetId,
  UCHAR Lun
);
```

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`TargetId`

Specifies the target identifier of the device.

`Lun`

Specifies the logical unit number (LUN) of the device.


## Return Value

None

## Remarks

The port driver resumes the paused request queue for the indicated device. If the caller assigns a wildcard value of IDE_UNTAGGED to parameters <i>TargetId</i> and <i>Lun</i>, the port driver will restart the channel request queue.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550155">AtaPortDeviceBusy</a>