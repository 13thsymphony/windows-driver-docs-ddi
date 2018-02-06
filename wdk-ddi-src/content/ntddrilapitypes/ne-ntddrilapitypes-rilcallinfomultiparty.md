---
UID: NE:ntddrilapitypes.RILCALLINFOMULTIPARTY
title: RILCALLINFOMULTIPARTY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfomultiparty.htm
old-project: netvista
ms.assetid: 4a343e55-9150-4411-bf37-f410b94ca0aa
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ntddrilapitypes/RILCALLINFOMULTIPARTY, ntddrilapitypes/RIL_CALL_MAX, RILCALLINFOMULTIPARTY, RIL_CALL_MAX, ntddrilapitypes/RIL_CALL_MULTIPARTY, RIL_CALL_MULTIPARTY, RILCALLINFOMULTIPARTY enumeration [Network Drivers Starting with Windows Vista], netvista.rilcallinfomultiparty
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
-	RILCALLINFOMULTIPARTY
product: Windows
targetos: Windows
req.typenames: RILCALLINFOMULTIPARTY
---

# RILCALLINFOMULTIPARTY Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLINFOMULTIPARTY { 
  RIL_CALL_MULTIPARTY,
  RIL_CALL_MAX
} RILCALLINFOMULTIPARTY;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CALL_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_MULTIPARTY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALL_SINGLEPARTY</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |