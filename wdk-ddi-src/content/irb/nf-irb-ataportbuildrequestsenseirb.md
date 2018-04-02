---
UID: NF:irb.AtaPortBuildRequestSenseIrb
title: AtaPortBuildRequestSenseIrb function
author: windows-driver-content
description: The AtaPortBuildRequestSenseIrb routine builds and returns an IRB for operation code SCSIOP_REQUEST_SENSE.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportbuildrequestsenseirb.htm
old-project: storage
ms.assetid: f5083841-a6d7-4437-9941-bd7dca2f1771
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: AtaPortBuildRequestSenseIrb, AtaPortBuildRequestSenseIrb routine [Storage Devices], atartns_82b5c3cd-1956-47a0-9c05-cd18dbb2e2b6.xml, irb/AtaPortBuildRequestSenseIrb, storage.ataportbuildrequestsenseirb
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
-	AtaPortBuildRequestSenseIrb
product:
- Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortBuildRequestSenseIrb function
The <b>AtaPortBuildRequestSenseIrb</b> routine builds and returns an IRB for operation code SCSIOP_REQUEST_SENSE.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

```
_IRQL_requires_same_ PIDE_REQUEST_BLOCK AtaPortBuildRequestSenseIrb(
  PVOID              ChannelExtension,
  PIDE_REQUEST_BLOCK Irb
);
```

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`Irb`

A pointer to a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff559140">IDE_REQUEST_BLOCK</a> that defines the failed IDE request block (IRB) for which the request sense will be issued.


## Return Value

If the operation succeeds, the <b>AtaPortBuildRequestSenseIrb</b> routine returns a pointer to the request sense IRB that it allocated. If the operation fails, <b>AtaPortBuildRequestSenseIrb</b> returns <b>NULL</b>.

## Remarks

If the device does not support auto request sense, the miniport driver must build an IRB to gather sense data by using <b>AtaPortBuildRequestSenseIrb</b> and then sending it to the device. The miniport driver must not complete the original IRB until the corresponding request sense IRB has completed. Be aware that no request sense data is required for ATA devices.

For an explanation of the SCSIOP_REQUEST_SENSE command, see the <i>SCSI-3</i> specification.

The miniport driver can have only one outstanding request sense IRB per logical unit.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff550217">AtaPortReleaseRequestSenseIrb</a>