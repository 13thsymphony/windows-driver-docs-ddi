---
UID: NE:rilapitypes.RILEMERGENCYNUMBERCATEGORY
title: RILEMERGENCYNUMBERCATEGORY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilemergencynumbercategory_2.htm
old-project: netvista
ms.assetid: 322e2622-1f9a-433a-8fe9-9d59c00ce8be
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_ENUM_MARINE_GUARD, rilapitypes/RIL_ENUM_AMBULANCE, RIL_ENUM_MANUAL_ECALL, rilapitypes/RIL_ENUM_ALL, RIL_ENUM_MOUNTAIN_RESCUE, RILEMERGENCYNUMBERCATEGORY enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RILEMERGENCYNUMBERCATEGORY, rilapitypes/RIL_ENUM_MOUNTAIN_RESCUE, RILEMERGENCYNUMBERCATEGORY, RIL_ENUM_FIRE_BRIGADE, RIL_ENUM_AUTO_ECALL, rilapitypes/RIL_ENUM_FIRE_BRIGADE, rilapitypes/RIL_ENUM_AUTO_ECALL, RIL_ENUM_AMBULANCE, RIL_ENUM_ALL, netvista.rilemergencynumbercategory_2, rilapitypes/RIL_ENUM_MARINE_GUARD, rilapitypes/RIL_ENUM_MANUAL_ECALL
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
req.include-header: 
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILEMERGENCYNUMBERCATEGORY
product: Windows
targetos: Windows
req.typenames: RILEMERGENCYNUMBERCATEGORY
req.product: Windows 10 or later.
---

# RILEMERGENCYNUMBERCATEGORY Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEMERGENCYNUMBERCATEGORY { 
  RIL_ENUM_AMBULANCE,
  RIL_ENUM_FIRE_BRIGADE,
  RIL_ENUM_MARINE_GUARD,
  RIL_ENUM_MOUNTAIN_RESCUE,
  RIL_ENUM_MANUAL_ECALL,
  RIL_ENUM_AUTO_ECALL,
  RIL_ENUM_ALL
} RILEMERGENCYNUMBERCATEGORY;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_ENUM_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ENUM_AMBULANCE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ENUM_AUTO_ECALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ENUM_FIRE_BRIGADE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ENUM_MANUAL_ECALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ENUM_MARINE_GUARD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ENUM_MOUNTAIN_RESCUE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_ENUM_POLICE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |