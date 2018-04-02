---
UID: NE:rilapitypes.RILSIGNALQUALITYCAPS
title: RILSIGNALQUALITYCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalqualitycaps.htm
old-project: netvista
ms.assetid: 5d42e083-d1a9-455a-8511-9aef37908ab7
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILSIGNALQUALITYCAPS, RILSIGNALQUALITYCAPS enumeration [Network Drivers Starting with Windows Vista], RIL_CAPS_SIGNALQUALITY_MAX, RIL_CAPS_SIGNALQUALITY_POLLING, netvista.rilsignalqualitycaps, ntddrilapitypes/RILSIGNALQUALITYCAPS, ntddrilapitypes/RIL_CAPS_SIGNALQUALITY_MAX, ntddrilapitypes/RIL_CAPS_SIGNALQUALITY_POLLING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: rilapitypes.h
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
-	RILSIGNALQUALITYCAPS
product: Windows
targetos: Windows
req.typenames: RILSIGNALQUALITYCAPS
req.product: Windows 10 or later.
---

# RILSIGNALQUALITYCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILSIGNALQUALITYCAPS {
  RIL_CAPS_SIGNALQUALITY_NOTIFICATION  ,
  RIL_CAPS_SIGNALQUALITY_POLLING       ,
  RIL_CAPS_SIGNALQUALITY_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_CAPS_SIGNALQUALITY_NOTIFICATION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_SIGNALQUALITY_POLLING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_SIGNALQUALITY_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |