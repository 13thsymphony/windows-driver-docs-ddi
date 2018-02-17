---
UID: NE:ntddrilapitypes.RILCALLMEDIAAUDIOFLAGS
title: RILCALLMEDIAAUDIOFLAGS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediaaudioflags.htm
old-project: netvista
ms.assetid: 457d0bee-4746-424d-bd22-4e968048bdb9
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMEDIAAUDIOFLAGS, ntddrilapitypes/RIL_CALLMEDIAAUDIOFLAG_TEMPORARILY_UNAVAILABLE, RILCALLMEDIAAUDIOFLAGS enumeration [Network Drivers Starting with Windows Vista], ntddrilapitypes/RIL_CALLMEDIAAUDIOFLAG_ALL, RIL_CALLMEDIAAUDIOFLAG_ALL, netvista.rilcallmediaaudioflags, ntddrilapitypes/RILCALLMEDIAAUDIOFLAGS, RIL_CALLMEDIAAUDIOFLAG_TEMPORARILY_UNAVAILABLE
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
-	RILCALLMEDIAAUDIOFLAGS
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAAUDIOFLAGS
---

# RILCALLMEDIAAUDIOFLAGS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLMEDIAAUDIOFLAGS { 
  RIL_CALLMEDIAAUDIOFLAG_TEMPORARILY_UNAVAILABLE,
  RIL_CALLMEDIAAUDIOFLAG_ALL
} RILCALLMEDIAAUDIOFLAGS;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CALLMEDIAAUDIOFLAG_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAAUDIOFLAG_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIAAUDIOFLAG_TEMPORARILY_UNAVAILABLE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |