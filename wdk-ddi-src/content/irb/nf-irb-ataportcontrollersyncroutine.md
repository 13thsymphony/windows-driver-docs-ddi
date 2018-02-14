---
UID: NF:irb.AtaPortControllerSyncRoutine
title: AtaPortControllerSyncRoutine function
author: windows-driver-content
description: The AtaPortControllerSyncRoutine routine provides synchronized access to data structures that are shared across all channels on a controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportcontrollersyncroutine.htm
old-project: storage
ms.assetid: 6b39e89e-21cc-404f-b9fc-6cad0b5c8d22
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortControllerSyncRoutine routine [Storage Devices], storage.ataportcontrollersyncroutine, AtaPortControllerSyncRoutine, atartns_1fdbc2cb-49db-4121-aaaa-8a50c2a6cbde.xml, irb/AtaPortControllerSyncRoutine
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
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
| **Library** | NtosKrnl.exe |

## See Also

<a href="..\irb\nf-irb-ataportrequestsynchronizedroutine.md">AtaPortRequestSynchronizedRoutine</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortControllerSyncRoutine routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>