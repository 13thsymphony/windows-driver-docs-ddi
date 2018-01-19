---
UID : NF:irb.AtaPortControllerSyncRoutine
title : AtaPortControllerSyncRoutine function
author : windows-driver-content
description : The AtaPortControllerSyncRoutine routine provides synchronized access to data structures that are shared across all channels on a controller.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location : storage\ataportcontrollersyncroutine.htm
old-project : storage
ms.assetid : 6b39e89e-21cc-404f-b9fc-6cad0b5c8d22
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : AtaPortControllerSyncRoutine
ms.prod : windows-hardware
ms.technology : windows-devices
ms.topic : function
req.header : irb.h
req.include-header : Ata.h, Irb.h
req.target-type : Desktop
req.target-min-winverclnt : 
req.target-min-winversvr : 
req.kmdf-ver : 
req.umdf-ver : 
req.alt-api : AtaPortControllerSyncRoutine
req.alt-loc : irb.h
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : 
req.dll : 
req.irql : 
req.typenames : IDE_POWER_STATE
---


# AtaPortControllerSyncRoutine function
The <b>AtaPortControllerSyncRoutine</b> routine provides synchronized access to data structures that are shared across all channels on a controller.

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




## Return Value

None

## Remarks

The miniport driver uses this routine to synchronize access to data structures that are shared across channels on a controller. The miniport driver, however, should use this routine very sparingly.

The <i>ControllerSyncRoutine</i> function pointer is declared in <i>Irb.h</i> as follows:

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows Driver kit version** |  |
| **Target platform** | Desktop |
| **Minimum KMDF version** |  |
| **Minimum UMDF version** |  |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** |  |
| **IRQL** |  |
| **DDI compliance rules** |  |

## See Also

<dl>
<dt>
<a href="..\irb\nf-irb-ataportrequestsynchronizedroutine.md">AtaPortRequestSynchronizedRoutine</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortControllerSyncRoutine routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>