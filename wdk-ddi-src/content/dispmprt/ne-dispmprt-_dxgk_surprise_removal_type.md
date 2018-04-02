---
UID: NE:dispmprt._DXGK_SURPRISE_REMOVAL_TYPE
title: "_DXGK_SURPRISE_REMOVAL_TYPE"
author: windows-driver-content
description: Indicates the type of surprise removal event when an external display device is disconnected from the system.
old-location: display\dxgk_surprise_removal_type.htm
old-project: display
ms.assetid: 3045f46d-d78a-4f07-9838-f3afd97d9244
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: DXGK_SURPRISE_REMOVAL_TYPE, DXGK_SURPRISE_REMOVAL_TYPE enumeration [Display Devices], DxgkRemovalHibernation, _DXGK_SURPRISE_REMOVAL_TYPE, display.dxgk_surprise_removal_type, dispmprt/DXGK_SURPRISE_REMOVAL_TYPE, dispmprt/DxgkRemovalHibernation
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: dispmprt.h
req.include-header: Dispmprt.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Dispmprt.h
api_name:
-	DXGK_SURPRISE_REMOVAL_TYPE
product:
- Windows
targetos: Windows
req.typenames: DXGK_SURPRISE_REMOVAL_TYPE
---

# _DXGK_SURPRISE_REMOVAL_TYPE Enumeration
Indicates the type of surprise removal event when an external display device is disconnected  from the system.

## Syntax
```
typedef enum _DXGK_SURPRISE_REMOVAL_TYPE {
  DxgkRemovalHibernation  ,
  DxgkRemovalPnPNotify
} DXGK_SURPRISE_REMOVAL_TYPE;
```

## Constants

<table>
            
                <tr>
                    <td>DxgkRemovalHibernation</td>
                    <td>The disconnected external display device was in hibernation mode.</td>
                </tr>
            
                <tr>
                    <td>DxgkRemovalPnPNotify</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Windows version** | Windows 8 Windows 8 |
| **Header** | dispmprt.h (include Dispmprt.h) |