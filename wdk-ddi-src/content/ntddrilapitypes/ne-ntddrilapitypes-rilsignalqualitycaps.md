---
UID: NE:ntddrilapitypes.RILSIGNALQUALITYCAPS
title: RILSIGNALQUALITYCAPS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalqualitycaps.htm
old-project: netvista
ms.assetid: 5d42e083-d1a9-455a-8511-9aef37908ab7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILSIGNALQUALITYCAPS, RILSIGNALQUALITYCAPS enumeration [Network Drivers Starting with Windows Vista], netvista.rilsignalqualitycaps, ntddrilapitypes/RIL_CAPS_SIGNALQUALITY_MAX, RIL_CAPS_SIGNALQUALITY_MAX, ntddrilapitypes/RIL_CAPS_SIGNALQUALITY_POLLING, ntddrilapitypes/RILSIGNALQUALITYCAPS, RIL_CAPS_SIGNALQUALITY_POLLING
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddrilapitypes.h
apiname:
-	RILSIGNALQUALITYCAPS
product: Windows
targetos: Windows
req.typenames: RILSIGNALQUALITYCAPS
---

# RILSIGNALQUALITYCAPS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSIGNALQUALITYCAPS { 
  RIL_CAPS_SIGNALQUALITY_POLLING,
  RIL_CAPS_SIGNALQUALITY_MAX
} RILSIGNALQUALITYCAPS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CAPS_SIGNALQUALITY_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_SIGNALQUALITY_NOTIFICATION</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CAPS_SIGNALQUALITY_POLLING</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |