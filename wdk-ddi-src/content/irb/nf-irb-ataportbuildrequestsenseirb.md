---
UID: NF.irb.AtaPortBuildRequestSenseIrb
title: AtaPortBuildRequestSenseIrb function
author: windows-driver-content
description: The AtaPortBuildRequestSenseIrb routine builds and returns an IRB for operation code SCSIOP_REQUEST_SENSE.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportbuildrequestsenseirb.htm
old-project: storage
ms.assetid: f5083841-a6d7-4437-9941-bd7dca2f1771
ms.author: windowsdriverdev
ms.date: 11/15/2017
ms.keywords: AtaPortBuildRequestSenseIrb
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
req.alt-api: AtaPortBuildRequestSenseIrb
req.alt-loc: ataport.lib,ataport.dll,pciidex.lib,pciidex.dll
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
---

# AtaPortBuildRequestSenseIrb function



## -description
The <b>AtaPortBuildRequestSenseIrb</b> routine builds and returns an IRB for operation code SCSIOP_REQUEST_SENSE.


## -syntax

````
PIDE_REQUEST_BLOCK AtaPortBuildRequestSenseIrb(
  _In_ PVOID              ChannelExtension,
  _In_ PIDE_REQUEST_BLOCK Irb
);
````


## -parameters

### -param ChannelExtension [in]

A pointer to the channel extension.

### -param Irb [in]

A pointer to a structure of type <a href="storage.ide_request_block">IDE_REQUEST_BLOCK</a> that defines the failed IDE request block (IRB) for which the request sense will be issued.

## -returns
If the operation succeeds, the <b>AtaPortBuildRequestSenseIrb</b> routine returns a pointer to the request sense IRB that it allocated. If the operation fails, <b>AtaPortBuildRequestSenseIrb</b> returns <b>NULL</b>.

## -remarks
If the device does not support auto request sense, the miniport driver must build an IRB to gather sense data by using <b>AtaPortBuildRequestSenseIrb</b> and then sending it to the device. The miniport driver must not complete the original IRB until the corresponding request sense IRB has completed. Be aware that no request sense data is required for ATA devices.

For an explanation of the SCSIOP_REQUEST_SENSE command, see the <i>SCSI-3</i> specification.

The miniport driver can have only one outstanding request sense IRB per logical unit.

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
<tr>
<th width="30%">
Library
</th>
<td width="70%">
<dl>
<dt>Ataport.lib; </dt>
<dt>Pciidex.lib</dt>
</dl>
</td>
</tr>
</table>

## -see-also
<dl>
<dt>
<a href="storage.ataportreleaserequestsenseirb">AtaPortReleaseRequestSenseIrb</a>
</dt>
</dl>
 
 
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortBuildRequestSenseIrb routine%20 RELEASE:%20(11/15/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>
