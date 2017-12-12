---
UID: NF.irb.AtaPortAllocateQueueTag
title: AtaPortAllocateQueueTag function
author: windows-driver-content
description: The AtaPortAllocateQueueTag routine returns a queue tag for the specified device.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportallocatequeuetag.htm
old-project: storage
ms.assetid: e298f51b-58b7-4f04-85d3-3ee809deb489
ms.author: windowsdriverdev
ms.date: 12/8/2017
ms.keywords: AtaPortAllocateQueueTag
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
req.alt-api: AtaPortAllocateQueueTag
req.alt-loc: irb.h
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
---

# AtaPortAllocateQueueTag function



## -description
The <b>AtaPortAllocateQueueTag</b> routine returns a queue tag for the specified device.



## -syntax

````
UCHAR AtaPortAllocateQueueTag(
  _In_ PVOID ChannelExtension,
  _In_ UCHAR TargetId,
  _In_ UCHAR Lun
);
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension.


### -param TargetId [in]

Specifies the target identifier of the device.


### -param Lun [in]

Specifies the logical unit number (LUN) of the device.


## -returns
<b>AtaPortAllocateQueueTag</b> returns a valid queue tag if one can be allocated. A value of 0 is returned if a queue tag could not be allocated. 


## -remarks
The <b>AtaPortAllocateQueueTag</b> routine allocates either a per device queue tag or a per channel queue tag. To generate a per channel queue tag, the miniport driver should set the <i>TargetId</i> and <i>Lun</i> parameters to IDE_UNTAGGED. 


## -requirements
<table>
<tr>
<th width="30%">
Target platform

</th>
<td width="70%">
<dl>
<dt>Desktop</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
Header

</th>
<td width="70%">
<dl>
<dt>Irb.h (include Ata.h or Irb.h)</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.ataportinitializequeuetag">AtaPortInitializeQueueTag</a>
</dt>
<dt>
<a href="storage.ataportreleasequeuetag">AtaPortReleaseQueueTag</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortAllocateQueueTag routine%20 RELEASE:%20(12/8/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

