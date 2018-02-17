---
UID: NF:irb.AtaPortReadRegisterBufferUchar
title: AtaPortReadRegisterBufferUchar function
author: windows-driver-content
description: The AtaPortReadRegisterBufferUchar routine transfers a specified number of unsigned bytes from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterbufferuchar.htm
old-project: storage
ms.assetid: adc6724b-f3dc-4605-8ee1-198c88bc3fcd
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: AtaPortReadRegisterBufferUchar, atartns_5c57e652-3b37-4673-b5cf-fbcdf38853ad.xml, storage.ataportreadregisterbufferuchar, irb/AtaPortReadRegisterBufferUchar, AtaPortReadRegisterBufferUchar routine [Storage Devices]
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
-	AtaPortReadRegisterBufferUchar
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortReadRegisterBufferUchar function
The <b>AtaPortReadRegisterBufferUchar</b> routine transfers a specified number of unsigned bytes from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID AtaPortReadRegisterBufferUchar(
  _In_ PUCHAR Register,
  _In_ PUCHAR Buffer,
  _In_ ULONG  Count
);
````

## Parameters

`Register`

Contains the register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.

`Buffer`

A pointer to the destination buffer.

`Count`

Specifies the number of bytes to read from the HBA.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportreadregisterbufferulong.md">AtaPortReadRegisterBufferUlong</a>



<a href="..\irb\nf-irb-ataportreadregisterbufferushort.md">AtaPortReadRegisterBufferUshort</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReadRegisterBufferUchar routine%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>