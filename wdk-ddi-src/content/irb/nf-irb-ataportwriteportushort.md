---
UID: NF:irb.AtaPortWritePortUshort
title: AtaPortWritePortUshort function
author: windows-driver-content
description: The AtaPortWritePortUshort routine transfers a USHORT value to the HBA.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ataportwriteportushort.htm
old-project: storage
ms.assetid: 14b47f0a-5de8-4650-8a90-40e9da8537f1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: irb/AtaPortWritePortUshort, AtaPortWritePortUshort, AtaPortWritePortUshort routine [Storage Devices], storage.ataportwriteportushort, atartns_1766efcd-f235-43ae-8fbe-ab56a858a7ee.xml
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
-	AtaPortWritePortUshort
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---


# AtaPortWritePortUshort function
The <b>AtaPortWritePortUshort</b> routine transfers a USHORT value to the HBA.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax

````
VOID AtaPortWritePortUshort(
  _In_ PUSHORT Port,
  _In_ USHORT  Value
);
````

## Parameters

`Port`

A pointer to the I/O port. The address value that is assigned to this parameter must be within the range of mapped I/O space addresses that are obtained by a call to <a href="..\irb\nf-irb-ataportgetdevicebase.md">AtaPortGetDeviceBase</a>.

`Value`

Specifies the value to write to the HBA's I/O port.


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



<a href="..\irb\nf-irb-ataportwriteportulong.md">AtaPortWritePortUlong</a>



<a href="..\irb\nf-irb-ataportwriteportuchar.md">AtaPortWritePortUchar</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20AtaPortWritePortUshort routine%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>