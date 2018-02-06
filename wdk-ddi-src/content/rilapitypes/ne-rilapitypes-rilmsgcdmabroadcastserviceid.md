---
UID: NE:rilapitypes.RILMSGCDMABROADCASTSERVICEID
title: RILMSGCDMABROADCASTSERVICEID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmabroadcastserviceid_2.htm
old-project: netvista
ms.assetid: d991a0f6-54ba-4951-8bdb-865a537d797a
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILMSGCDMABROADCASTSERVICEID, RIL_1xBROADCAST_CMAS_SEVERE, RIL_1xBROADCAST_CMAS_EXTREME, RILMSGCDMABROADCASTSERVICEID, RIL_1xBROADCAST_CMAS_TEST, rilapitypes/RIL_1xBROADCAST_CMAS_TEST, RILMSGCDMABROADCASTSERVICEID enumeration [Network Drivers Starting with Windows Vista], RIL_1xBROADCAST_CMAS_AMBER, rilapitypes/RIL_1xBROADCAST_CMAS_EXTREME, rilapitypes/RIL_1xBROADCAST_CMAS_SEVERE, rilapitypes/RIL_1xBROADCAST_CMAS_AMBER, netvista.rilmsgcdmabroadcastserviceid_2
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
-	RILMSGCDMABROADCASTSERVICEID
product: Windows
targetos: Windows
req.typenames: RILMSGCDMABROADCASTSERVICEID
req.product: Windows 10 or later.
---

# RILMSGCDMABROADCASTSERVICEID Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGCDMABROADCASTSERVICEID { 
  RIL_1xBROADCAST_CMAS_EXTREME,
  RIL_1xBROADCAST_CMAS_SEVERE,
  RIL_1xBROADCAST_CMAS_AMBER,
  RIL_1xBROADCAST_CMAS_TEST
} RILMSGCDMABROADCASTSERVICEID;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_AMBER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_EXTREME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_PRESIDENTIAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_SEVERE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_TEST</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |