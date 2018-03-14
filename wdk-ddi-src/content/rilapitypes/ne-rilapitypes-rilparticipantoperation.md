---
UID: NE:rilapitypes.RILPARTICIPANTOPERATION
title: RILPARTICIPANTOPERATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilparticipantoperation.htm
old-project: netvista
ms.assetid: 0f59d104-ef86-4fed-9728-1a01ccb6f879
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILPARTICIPANTOPERATION, RILPARTICIPANTOPERATION enumeration [Network Drivers Starting with Windows Vista], RIL_PARTICIPANT_MAX, RIL_PARTICIPANT_REMOVE, netvista.rilparticipantoperation, ntddrilapitypes/RILPARTICIPANTOPERATION, ntddrilapitypes/RIL_PARTICIPANT_MAX, ntddrilapitypes/RIL_PARTICIPANT_REMOVE
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
-	RILPARTICIPANTOPERATION
product: Windows
targetos: Windows
req.typenames: RILPARTICIPANTOPERATION
req.product: Windows 10 or later.
---

# RILPARTICIPANTOPERATION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILPARTICIPANTOPERATION { 
  RIL_PARTICIPANT_REMOVE,
  RIL_PARTICIPANT_MAX
} RILPARTICIPANTOPERATION;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARTICIPANT_ADD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARTICIPANT_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARTICIPANT_REMOVE</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |