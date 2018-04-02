---
UID: NE:ntddrilapitypes.RILPHONEBOOKLOCATIONCAPS
title: RILPHONEBOOKLOCATIONCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilphonebooklocationcaps.htm
old-project: netvista
ms.assetid: df2f059c-d1c3-4716-8254-47c71f0b4a7c
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILPHONEBOOKLOCATIONCAPS, RILPHONEBOOKLOCATIONCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_CAPS_PBLOC_ALL, RIL_CAPS_PBLOC_OWNNUMBERS, RIL_CAPS_PBLOC_UICCFIXDIALING, RIL_CAPS_PBLOC_UICCPHONEBOOK, RIL_CAPS_PBLOC_UICCSERVICEDIALING, netvista.rilphonebooklocationcaps, ntddrilapitypes/RILPHONEBOOKLOCATIONCAPS, ntddrilapitypes/RIL_CAPS_PBLOC_ALL, ntddrilapitypes/RIL_CAPS_PBLOC_OWNNUMBERS, ntddrilapitypes/RIL_CAPS_PBLOC_UICCFIXDIALING, ntddrilapitypes/RIL_CAPS_PBLOC_UICCPHONEBOOK, ntddrilapitypes/RIL_CAPS_PBLOC_UICCSERVICEDIALING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILPHONEBOOKLOCATIONCAPS
product:
- Windows
targetos: Windows
req.typenames: RILPHONEBOOKLOCATIONCAPS
---

# RILPHONEBOOKLOCATIONCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILPHONEBOOKLOCATIONCAPS {
  RIL_CAPS_PBLOC_UNKOWN              ,
  RIL_CAPS_PBLOC_UICCFIXDIALING      ,
  RIL_CAPS_PBLOC_OWNNUMBERS          ,
  RIL_CAPS_PBLOC_UICCPHONEBOOK       ,
  RIL_CAPS_PBLOC_UICCSERVICEDIALING  ,
  RIL_CAPS_PBLOC_ALL
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_CAPS_PBLOC_UNKOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PBLOC_UICCFIXDIALING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PBLOC_OWNNUMBERS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PBLOC_UICCPHONEBOOK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PBLOC_UICCSERVICEDIALING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_PBLOC_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |