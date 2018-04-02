---
UID: NE:irb.IDE_CONTROL_ACTION
title: IDE_CONTROL_ACTION
author: windows-driver-content
description: The IDE_CONTROL_ACTION enumeration type indicates the control action to be performed by a IdeHwControl routine.Note  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future.
old-location: storage\ide_control_action.htm
old-project: storage
ms.assetid: a63d1a2f-d560-492f-9b73-198e42cb4300
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: IDE_CONTROL_ACTION, IDE_CONTROL_ACTION enumeration [Storage Devices], IdePowerDown, IdePowerUp, IdeStart, IdeStop, IdeVendorDefined, irb/IDE_CONTROL_ACTION, irb/IdePowerDown, irb/IdePowerUp, irb/IdeStart, irb/IdeStop, irb/IdeVendorDefined, storage.ide_control_action, structs-ATA_f5df2197-3199-4b3f-ba0a-7a92cd75e3ac.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	irb.h
api_name:
-	IDE_CONTROL_ACTION
product:
- Windows
targetos: Windows
req.typenames: IDE_CONTROL_ACTION
---

# IDE_CONTROL_ACTION Enumeration
The IDE_CONTROL_ACTION enumeration type indicates the control action to be performed by a <a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a> routine.
<div class="alert"><b>Note</b>  The ATA port driver and ATA miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
```
typedef enum IDE_CONTROL_ACTION {
  IdeStart          ,
  IdeStop           ,
  IdePowerUp        ,
  IdePowerDown      ,
  IdeVendorDefined
} ;
```

## Constants

<table>
            
                <tr>
                    <td>IdeStart</td>
                    <td>Indicates that the miniport driver should start the channel.</td>
                </tr>
            
                <tr>
                    <td>IdeStop</td>
                    <td>Indicates that the miniport driver should stop the channel.</td>
                </tr>
            
                <tr>
                    <td>IdePowerUp</td>
                    <td>Indicates that the miniport driver should power up the channel.</td>
                </tr>
            
                <tr>
                    <td>IdePowerDown</td>
                    <td>Indicates that the miniport driver should power down the channel.</td>
                </tr>
            
                <tr>
                    <td>IdeVendorDefined</td>
                    <td>Indicates that the miniport driver should perform a vendor-defined control action.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | irb.h (include Irb.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff557465">IdeHwControl</a>