---
UID: NE:rilapitypes.RILMSGMWIPRIORITY
title: RILMSGMWIPRIORITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgmwipriority_2.htm
old-project: netvista
ms.assetid: a9efeb68-8838-476f-8ffb-11c8c71163fc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_MSGMWIPRIORITY_MAX, netvista.rilmsgmwipriority_2, rilapitypes/RIL_MSGMWIPRIORITY_MAX, rilapitypes/RILMSGMWIPRIORITY, rilapitypes/RIL_MSGMWIPRIORITY_URGENT, RIL_MSGMWIPRIORITY_EMERGENCY, RIL_MSGMWIPRIORITY_NORMAL, RIL_MSGMWIPRIORITY_URGENT, RIL_MSGMWIPRIORITY_LOW, rilapitypes/RIL_MSGMWIPRIORITY_LOW, rilapitypes/RIL_MSGMWIPRIORITY_NORMAL, RILMSGMWIPRIORITY, RILMSGMWIPRIORITY enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_MSGMWIPRIORITY_EMERGENCY
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
                    <td>RIL_MSGMWIPRIORITY_EMERGENCY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_LOW</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_NORMAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGMWIPRIORITY_URGENT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |