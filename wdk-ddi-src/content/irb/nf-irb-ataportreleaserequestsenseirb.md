---
UID: NF:irb.AtaPortReleaseRequestSenseIrb
title: AtaPortReleaseRequestSenseIrb function
author: windows-driver-content
description: The AtaPortReleaseRequestSenseIrb routine frees the request sense IRB tha is allocated by using AtaPortBuildRequestSenseIrb.
old-location: storage\ataportreleaserequestsenseirb.htm
old-project: storage
ms.assetid: 53e5e234-c256-4581-b109-307f2f17522f
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortReleaseRequestSenseIrb routine [Storage Devices], irb/AtaPortReleaseRequestSenseIrb, AtaPortReleaseRequestSenseIrb, storage.ataportreleaserequestsenseirb, atartns_b46ae59d-b5b8-49fb-9458-742eefacd197.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ataport.lib
-	ataport.dll
-	pciidex.lib
-	pciidex.dll
apiname:
-	AtaPortReleaseRequestSenseIrb
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortReleaseRequestSenseIrb function
The <b>AtaPortReleaseRequestSenseIrb</b> routine frees the request sense IRB tha is allocated by using <a href="..\irb\nf-irb-ataportbuildrequestsenseirb.md">AtaPortBuildRequestSenseIrb</a>. 
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID AtaPortReleaseRequestSenseIrb(
  _In_ PVOID              ChannelExtension,
  _In_ PIDE_REQUEST_BLOCK Irb
);
````

## Parameters

`ChannelExtension`

A pointer to the channel extension.

`Irb`

A pointer to a structure of type <a href="..\irb\ns-irb-_ide_request_block.md">IDE_REQUEST_BLOCK</a> that defines the request sense IRB.


## Return Value

None

## Remarks

The <b>AtaPortReleaseRequestSenseIrb</b> routine releases the IRB to the port driver and copies the sense data to the buffer that is pointed to by the <b>SenseInfoBuffer</b> member of the original (failed) request's IRB. The miniport driver can then complete the original request by using <a href="..\irb\nf-irb-ataportcompleterequest.md">AtaPortCompleteRequest</a>. The miniport driver must not touch the request sense IRB after it has been released to the port driver.

The miniport driver must call <b>AtaPortReleaseRequestSenseIrb</b> for every allocated IRB that is allocated by using <a href="..\irb\nf-irb-ataportbuildrequestsenseirb.md">AtaPortBuildRequestSenseIrb</a>.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="..\irb\nf-irb-ataportbuildrequestsenseirb.md">AtaPortBuildRequestSenseIrb</a>

<a href="..\irb\nf-irb-ataportcompleterequest.md">AtaPortCompleteRequest</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReleaseRequestSenseIrb routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>