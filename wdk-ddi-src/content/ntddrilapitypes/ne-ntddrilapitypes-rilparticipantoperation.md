---
UID: NE:ntddrilapitypes.RILPARTICIPANTOPERATION
title: RILPARTICIPANTOPERATION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilparticipantoperation.htm
old-project: netvista
ms.assetid: 0f59d104-ef86-4fed-9728-1a01ccb6f879
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RIL_PARTICIPANT_REMOVE, ntddrilapitypes/RILPARTICIPANTOPERATION, netvista.rilparticipantoperation, RILPARTICIPANTOPERATION, ntddrilapitypes/RIL_PARTICIPANT_MAX, RIL_PARTICIPANT_REMOVE, RIL_PARTICIPANT_MAX, RILPARTICIPANTOPERATION enumeration [Network Drivers Starting with Windows Vista]
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
-	RILPARTICIPANTOPERATION
product: Windows
targetos: Windows
req.typenames: RILPARTICIPANTOPERATION
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
| **Header** | ntddrilapitypes.h |