---
UID: NF:irb.AtaPortReadRegisterBufferUshort
title: AtaPortReadRegisterBufferUshort function
author: windows-driver-content
description: The AtaPortReadRegisterBufferUshort routine transfers a specified number of USHORT values from the HBA to a buffer.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportreadregisterbufferushort.htm
old-project: storage
ms.assetid: bd2e8fe0-7daf-4fdd-ac3a-893df6d0f10f
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: AtaPortReadRegisterBufferUshort, AtaPortReadRegisterBufferUshort routine [Storage Devices], atartns_4943b97d-90a0-44d9-adfa-d3bce57e88c9.xml, irb/AtaPortReadRegisterBufferUshort, storage.ataportreadregisterbufferushort
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
-	AtaPortReadRegisterBufferUshort
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortReadRegisterBufferUshort function
The <b>AtaPortReadRegisterBufferUshort</b> routine transfers a specified number of USHORT values from the HBA to a buffer.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID AtaPortReadRegisterBufferUshort(
  _In_ PUSHORT Register,
  _In_ PUSHORT Buffer,
  _In_ ULONG   Count
);
````

## Parameters

`Register`

Contains the register address where the transfer should begin. This address value must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.

`Buffer`

A pointer to the destination buffer.

`Count`

Specifies the number of USHORT values to read from the HBA.


## Return Value

None


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Target Platform** | Desktop |
| **Header** | irb.h (include Ata.h, Irb.h) |
| **Library** | Ataport.lib; Pciidex.lib |

## See Also

<a href="..\irb\nf-irb-ataportreadregisterbufferulong.md">AtaPortReadRegisterBufferUlong</a>



<a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>



<a href="..\irb\nf-irb-ataportreadregisterbufferuchar.md">AtaPortReadRegisterBufferUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortReadRegisterBufferUshort routine%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>