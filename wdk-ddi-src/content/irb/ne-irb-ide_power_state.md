---
UID: NE:irb.IDE_POWER_STATE
title: IDE_POWER_STATE
author: windows-driver-content
description: The IDE_POWER_STATE enumeration type indicates that power state of the device.
old-location: storage\ide_power_state.htm
old-project: storage
ms.assetid: b54655ac-b7ac-4026-9d9d-75dd139ac059
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: irb/IdePowerUnSpecified, storage.ide_power_state, irb/IdePowerD0, IDE_POWER_STATE enumeration [Storage Devices], structs-ATA_82594916-763d-46c4-9a40-e1e4f0c32e13.xml, irb/IDE_POWER_STATE, irb/IdePowerD3, IDE_POWER_STATE, IdePowerD3, IdePowerD0, IdePowerUnSpecified
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: irb.h
req.include-header: Irb.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	irb.h
apiname:
-	IDE_POWER_STATE
product: Windows
targetos: Windows
req.typenames: IDE_POWER_STATE
---

# IDE_POWER_STATE Enumeration
The IDE_POWER_STATE enumeration type indicates that power state of the device.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
````
typedef enum  { 
  IdePowerUnSpecified  = 0,
  IdePowerD0           = 1,
  IdePowerD3           = 2
} IDE_POWER_STATE;
````

## Constants

<table>
            
                <tr>
                    <td>IdePowerD0</td>
                    <td>Indicates a device power level of 0.</td>
                </tr>
            
                <tr>
                    <td>IdePowerD3</td>
                    <td>Indicates a device power level of 3.</td>
                </tr>
            
                <tr>
                    <td>IdePowerUnSpecified</td>
                    <td>Indicates that the power level is unspecified.</td>
                </tr>
</table>

    ## Remarks

        The IDE_POWER_STATE enumeration type is used in conjunction with the <a href="..\irb\nf-irb-ataportrequestpowerstatechange.md">AtaPortRequestPowerStateChange</a> routine to request a power state transition for a device.

## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | irb.h (include Irb.h) |

    ## See Also

        <a href="..\irb\nf-irb-ataportrequestpowerstatechange.md">AtaPortRequestPowerStateChange</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20IDE_POWER_STATE enumeration%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>