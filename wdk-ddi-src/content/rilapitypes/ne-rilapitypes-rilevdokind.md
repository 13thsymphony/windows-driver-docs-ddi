---
UID: NE:rilapitypes.RILEVDOKIND
title: RILEVDOKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilevdokind_2.htm
old-project: netvista
ms.assetid: df59e0f7-6e78-4098-9a2a-9a3143d66152
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_EVDOKIND_REVB, netvista.rilevdokind_2, rilapitypes/RIL_EVDOKIND_MAX, rilapitypes/RIL_EVDOKIND_REVA, RIL_EVDOKIND_REVA, RILEVDOKIND enumeration [Network Drivers Starting with Windows Vista], RIL_EVDOKIND_MAX, RILEVDOKIND, rilapitypes/RIL_EVDOKIND_REVB, rilapitypes/RILEVDOKIND
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
-	RILEVDOKIND
product: Windows
targetos: Windows
req.typenames: RILEVDOKIND
req.product: Windows 10 or later.
---

# RILEVDOKIND Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEVDOKIND { 
  RIL_EVDOKIND_REVA,
  RIL_EVDOKIND_REVB,
  RIL_EVDOKIND_MAX
} RILEVDOKIND;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_EVDOKIND_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EVDOKIND_REV0</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EVDOKIND_REVA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EVDOKIND_REVB</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |