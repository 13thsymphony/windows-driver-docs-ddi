---
UID: NE:rilapitypes.RILSMSREADYSTATE
title: RILSMSREADYSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsmsreadystate_2.htm
old-project: netvista
ms.assetid: 4b1fd540-85cf-45b3-9f39-984bb3b9e200
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilsmsreadystate_2, RIL_SMSREADY_UICCREADY, rilapitypes/RILSMSREADYSTATE, rilapitypes/RIL_SMSREADY_SERVICEREADY_3GPP2, RIL_SMSREADYSTATE_ALL, rilapitypes/RIL_SMSREADYSTATE_ALL, RILSMSREADYSTATE enumeration [Network Drivers Starting with Windows Vista], RILSMSREADYSTATE, rilapitypes/RIL_SMSREADY_UICCREADY, RIL_SMSREADY_SERVICEREADY_3GPP2
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
-	RILSMSREADYSTATE
product: Windows
targetos: Windows
req.typenames: RILSMSREADYSTATE
req.product: Windows 10 or later.
---

# RILSMSREADYSTATE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSMSREADYSTATE { 
  RIL_SMSREADY_SERVICEREADY_3GPP2,
  RIL_SMSREADY_UICCREADY,
  RIL_SMSREADYSTATE_ALL
} RILSMSREADYSTATE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SMSREADY_SERVICEREADY_3GPP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSREADY_SERVICEREADY_3GPP2</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSREADY_UICCREADY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SMSREADYSTATE_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |