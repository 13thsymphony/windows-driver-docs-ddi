---
UID: NE:ntddrilapitypes.RILCALLMEDIAOFFERACTION
title: RILCALLMEDIAOFFERACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaofferaction.htm
old-project: netvista
ms.assetid: 0a2ac234-633d-4ebc-9e13-05a12534f93a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_ASK, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_ERROR, RIL_CALLMEDIAOFFERACTION_REJECT, RIL_CALLMEDIAOFFERACTION_ERROR, RIL_CALLMEDIAOFFERACTION_ASK, RIL_CALLMEDIAOFFERACTION_ACCEPT, RIL_CALLMEDIAOFFERACTION_CANCEL, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_CANCEL, RILCALLMEDIAOFFERACTION enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_ACCEPT, ntddrilapitypes/RILCALLMEDIAOFFERACTION, RILCALLMEDIAOFFERACTION, netvista.rilcallmediaofferaction, RIL_CALLMEDIAOFFERACTION_MAX, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_MAX, ntddrilapitypes/RIL_CALLMEDIAOFFERACTION_REJECT
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
-	RILCALLMEDIAOFFERACTION
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAOFFERACTION
---

# RILCALLMEDIAOFFERACTION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLMEDIAOFFERACTION { 
  RIL_CALLMEDIAOFFERACTION_ERROR,
  RIL_CALLMEDIAOFFERACTION_REJECT,
  RIL_CALLMEDIAOFFERACTION_ASK,
  RIL_CALLMEDIAOFFERACTION_ACCEPT,
  RIL_CALLMEDIAOFFERACTION_CANCEL,
  RIL_CALLMEDIAOFFERACTION_MAX
} RILCALLMEDIAOFFERACTION;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CALLMEDIAOFFERACTION_ACCEPT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAOFFERACTION_ASK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAOFFERACTION_CANCEL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAOFFERACTION_ERROR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAOFFERACTION_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAOFFERACTION_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAOFFERACTION_REJECT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |