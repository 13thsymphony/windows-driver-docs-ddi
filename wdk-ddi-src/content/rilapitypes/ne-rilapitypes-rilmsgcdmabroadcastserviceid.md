---
UID: NE:rilapitypes.RILMSGCDMABROADCASTSERVICEID
title: RILMSGCDMABROADCASTSERVICEID
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgcdmabroadcastserviceid.htm
old-project: netvista
ms.assetid: 71f887ed-ab80-4b5f-bc74-d4333984fdd2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILMSGCDMABROADCASTSERVICEID, RILMSGCDMABROADCASTSERVICEID enumeration [Network Drivers Starting with Windows Vista], RIL_1xBROADCAST_CMAS_AMBER, RIL_1xBROADCAST_CMAS_EXTREME, RIL_1xBROADCAST_CMAS_SEVERE, RIL_1xBROADCAST_CMAS_TEST, netvista.rilmsgcdmabroadcastserviceid, ntddrilapitypes/RILMSGCDMABROADCASTSERVICEID, ntddrilapitypes/RIL_1xBROADCAST_CMAS_AMBER, ntddrilapitypes/RIL_1xBROADCAST_CMAS_EXTREME, ntddrilapitypes/RIL_1xBROADCAST_CMAS_SEVERE, ntddrilapitypes/RIL_1xBROADCAST_CMAS_TEST
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
                    <td>RIL_1xBROADCAST_CMAS_PRESIDENTIAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_EXTREME</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_SEVERE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_1xBROADCAST_CMAS_AMBER</td>
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
| **Header** | rilapitypes.h (include Rilapitypes.h) |