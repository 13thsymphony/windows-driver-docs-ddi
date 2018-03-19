---
UID: NE:rilapitypes.RILMSGMWIPRIORITY
title: RILMSGMWIPRIORITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwipriority.htm
old-project: netvista
ms.assetid: a974af39-a4a6-44f2-9010-e612f50c83df
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILMSGMWIPRIORITY, RILMSGMWIPRIORITY enumeration [Network Drivers Starting with Windows Vista], RIL_MSGMWIPRIORITY_EMERGENCY, RIL_MSGMWIPRIORITY_LOW, RIL_MSGMWIPRIORITY_MAX, RIL_MSGMWIPRIORITY_NORMAL, RIL_MSGMWIPRIORITY_URGENT, netvista.rilmsgmwipriority, ntddrilapitypes/RILMSGMWIPRIORITY, ntddrilapitypes/RIL_MSGMWIPRIORITY_EMERGENCY, ntddrilapitypes/RIL_MSGMWIPRIORITY_LOW, ntddrilapitypes/RIL_MSGMWIPRIORITY_MAX, ntddrilapitypes/RIL_MSGMWIPRIORITY_NORMAL, ntddrilapitypes/RIL_MSGMWIPRIORITY_URGENT
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
-	RILMSGMWIPRIORITY
product: Windows
targetos: Windows
req.typenames: RILMSGMWIPRIORITY
req.product: Windows 10 or later.
---

# RILMSGMWIPRIORITY Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGMWIPRIORITY { 
  RIL_MSGMWIPRIORITY_LOW,
  RIL_MSGMWIPRIORITY_NORMAL,
  RIL_MSGMWIPRIORITY_URGENT,
  RIL_MSGMWIPRIORITY_EMERGENCY,
  RIL_MSGMWIPRIORITY_MAX
} RILMSGMWIPRIORITY;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_LOW</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_NORMAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_URGENT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_EMERGENCY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |