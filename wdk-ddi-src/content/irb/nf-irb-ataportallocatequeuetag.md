---
UID: NF:irb.AtaPortAllocateQueueTag
title: AtaPortAllocateQueueTag function
author: windows-driver-content
description: The AtaPortAllocateQueueTag routine returns a queue tag for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportallocatequeuetag.htm
old-project: storage
ms.assetid: e298f51b-58b7-4f04-85d3-3ee809deb489
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortAllocateQueueTag, AtaPortAllocateQueueTag routine [Storage Devices], atartns_bae1e6d8-6ae5-4428-88a6-334a63fcefae.xml, irb/AtaPortAllocateQueueTag, storage.ataportallocatequeuetag
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
-	AtaPortAllocateQueueTag
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortAllocateQueueTag function
The <b>AtaPortAllocateQueueTag</b> routine returns a queue tag for the specified device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
_IRQL_requires_same_ UCHAR AtaPortAllocateQueueTag(
  PVOID DeviceExtension,
  UCHAR TargetId,
  UCHAR Lun
);
```

## Parameters

`DeviceExtension`

TBD

`TargetId`

Specifies the target identifier of the device.

`Lun`

Specifies the logical unit number (LUN) of the device.


## Return Value

<b>AtaPortAllocateQueueTag</b> returns a valid queue tag if one can be allocated. A value of 0 is returned if a queue tag could not be allocated.

## Remarks

The <b>AtaPortAllocateQueueTag</b> routine allocates either a per device queue tag or a per channel queue tag. To generate a per channel queue tag, the miniport driver should set the <i>TargetId</i> and <i>Lun</i> parameters to IDE_UNTAGGED.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550168">AtaPortInitializeQueueTag</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550214">AtaPortReleaseQueueTag</a>