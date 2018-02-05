---
UID : NF:irb.AtaPortReleaseQueueTag
title : AtaPortReleaseQueueTag function
author : windows-driver-content
description : The AtaPortReleaseQueueTag routine releases the specified queue tag.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location : storage\ataportreleasequeuetag.htm
old-project : storage
ms.assetid : 54399050-740f-4af8-ad85-cd3060f14af4
ms.author : windowsdriverdev
ms.date : 1/10/2018
ms.keywords : storage.ataportreleasequeuetag, irb/AtaPortReleaseQueueTag, AtaPortReleaseQueueTag, AtaPortReleaseQueueTag routine [Storage Devices], atartns_cfdd9be6-53b5-4c4a-ac61-bc6a3cf48ea5.xml
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
req.ddi-compliance : 
req.unicode-ansi : 
req.idl : 
req.max-support : 
req.namespace : 
req.assembly : 
req.type-library : 
req.lib : Ataport.lib; Pciidex.lib
req.dll : 
req.irql : 
topictype : 
apitype : 
apilocation : 
apiname : 
product : Windows
targetos : Windows
req.typenames : IDE_POWER_STATE
---


# AtaPortReleaseQueueTag function
The <b>AtaPortReleaseQueueTag</b> routine releases the specified queue tag.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID AtaPortReleaseQueueTag(
  _In_ PVOID ChannelExtension,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun,
  _In_ UCHAR QueueTag
);
````

## Parameters

`DeviceExtension`

TBD

`TargetId`

Specifies the target identifier of the device.

`Lun`

Specifies the logical unit number of the device.

`QueueTag`

Specifies the queue tag to be freed.


## Return Value

None

## Remarks

The miniport driver should call <b>AtaPortReleaseQueueTag</b> to free allocated queue tags by using <a href="..\irb\nf-irb-ataportallocatequeuetag.md">AtaPortAllocateQueueTag</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="..\irb\nf-irb-ataportinitializequeuetag.md">AtaPortInitializeQueueTag</a>

<a href="..\irb\nf-irb-ataportallocatequeuetag.md">AtaPortAllocateQueueTag</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReleaseQueueTag routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>