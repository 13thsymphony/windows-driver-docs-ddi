---
UID: NF:irb.AtaPortControllerSyncRoutine
title: AtaPortControllerSyncRoutine function
author: windows-driver-content
description: The AtaPortControllerSyncRoutine routine provides synchronized access to data structures that are shared across all channels on a controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportcontrollersyncroutine.htm
old-project: storage
ms.assetid: 6b39e89e-21cc-404f-b9fc-6cad0b5c8d22
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortControllerSyncRoutine, AtaPortControllerSyncRoutine routine [Storage Devices], atartns_1fdbc2cb-49db-4121-aaaa-8a50c2a6cbde.xml, irb/AtaPortControllerSyncRoutine, storage.ataportcontrollersyncroutine
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
-	AtaPortControllerSyncRoutine
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortControllerSyncRoutine function
The <b>AtaPortControllerSyncRoutine</b> routine provides synchronized access to data structures that are shared across all channels on a controller.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
BOOLEAN __inline AtaPortControllerSyncRoutine(
  _In_ PVOID      ChannelExtension,
  _In_ IDE_HW_DPC ControllerSyncRoutine
);
````

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`CallBackRoutine`

TBD


## Return Value

None

## Remarks

The miniport driver uses this routine to synchronize access to data structures that are shared across channels on a controller. The miniport driver, however, should use this routine very sparingly.

The <i>ControllerSyncRoutine</i> function pointer is declared in <i>Irb.h</i> as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>typedef
VOID
(*IDE_HW_DPC) (
  IN PVOID ChannelExtension
  );</pre>
</td>
</tr>
</table></span></div>

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |

## See Also

<a href="..\irb\nf-irb-ataportrequestsynchronizedroutine.md">AtaPortRequestSynchronizedRoutine</a>