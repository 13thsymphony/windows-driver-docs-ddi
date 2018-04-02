---
UID: NE:scsiwmi.SCSIWMI_ENABLE_DISABLE_CONTROL
title: SCSIWMI_ENABLE_DISABLE_CONTROL
author: windows-driver-content
description: The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable.
old-location: storage\scsiwmi_enable_disable_control.htm
old-project: storage
ms.assetid: 0327bdc0-e4a4-4c2f-a9b9-5854e3330068
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: SCSIWMI_ENABLE_DISABLE_CONTROL, SCSIWMI_ENABLE_DISABLE_CONTROL enumeration [Storage Devices], ScsiWmiDataBlockControl, ScsiWmiEventControl, scsiwmi/SCSIWMI_ENABLE_DISABLE_CONTROL, scsiwmi/ScsiWmiDataBlockControl, scsiwmi/ScsiWmiEventControl, storage.scsiwmi_enable_disable_control, structs-scsibus_58a70c92-6ee7-4385-b212-45672a12ac8b.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: scsiwmi.h
req.include-header: Scsiwmi.h
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
-	scsiwmi.h
api_name:
-	SCSIWMI_ENABLE_DISABLE_CONTROL
product:
- Windows
targetos: Windows
req.typenames: SCSIWMI_ENABLE_DISABLE_CONTROL
req.product: Windows 10 or later.
---

# SCSIWMI_ENABLE_DISABLE_CONTROL Enumeration
The SCSIWMI_ENABLE_DISABLE_CONTROL enumerator is used to specify what to enable or disable. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## Syntax
```
typedef enum SCSIWMI_ENABLE_DISABLE_CONTROL {
  ScsiWmiEventControl      ,
  ScsiWmiDataBlockControl
} ;
```

## Constants

<table>
            
                <tr>
                    <td>ScsiWmiEventControl</td>
                    <td>Indicates that a WMI event is to be enabled or disabled.</td>
                </tr>
            
                <tr>
                    <td>ScsiWmiDataBlockControl</td>
                    <td>Indicates that a data collection for a block is to be enabled or disabled.</td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | scsiwmi.h (include Scsiwmi.h) |

## See Also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff544094">DpWmiFunctionControl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557338">HwScsiWmiFunctionControl</a>