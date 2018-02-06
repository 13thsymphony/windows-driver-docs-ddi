---
UID: NE:ntddrilapitypes.RILPERSODEACTIVATIONSTATEDEPERSOSTATE
title: RILPERSODEACTIVATIONSTATEDEPERSOSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpersodeactivationstatedepersostate.htm
old-project: netvista
ms.assetid: 81147a47-b5aa-4f00-812d-2c6cf9d5ab8b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILPERSODEACTIVATIONSTATEDEPERSOSTATE, RIL_DEPERSOSTATE_PUK_BLOCKED, RIL_DEPERSOSTATE_PUK_REQUIRED, RIL_DEPERSOSTATE_MAX, ntddrilapitypes/RIL_DEPERSOSTATE_MAX, ntddrilapitypes/RIL_DEPERSOSTATE_PUK_REQUIRED, netvista.rilpersodeactivationstatedepersostate, RILPERSODEACTIVATIONSTATEDEPERSOSTATE, ntddrilapitypes/RIL_DEPERSOSTATE_PUK_BLOCKED, ntddrilapitypes/RIL_DEPERSOSTATE_CK_REQUIRED, RILPERSODEACTIVATIONSTATEDEPERSOSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_DEPERSOSTATE_CK_REQUIRED
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
-	RILPERSODEACTIVATIONSTATEDEPERSOSTATE
product: Windows
targetos: Windows
req.typenames: RILPERSODEACTIVATIONSTATEDEPERSOSTATE
---

# RILPERSODEACTIVATIONSTATEDEPERSOSTATE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILPERSODEACTIVATIONSTATEDEPERSOSTATE { 
  RIL_DEPERSOSTATE_CK_REQUIRED,
  RIL_DEPERSOSTATE_PUK_REQUIRED,
  RIL_DEPERSOSTATE_PUK_BLOCKED,
  RIL_DEPERSOSTATE_MAX
} RILPERSODEACTIVATIONSTATEDEPERSOSTATE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_DEPERSOSTATE_CK_REQUIRED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DEPERSOSTATE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DEPERSOSTATE_PUK_BLOCKED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DEPERSOSTATE_PUK_REQUIRED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DEPERSOSTATE_READY</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |