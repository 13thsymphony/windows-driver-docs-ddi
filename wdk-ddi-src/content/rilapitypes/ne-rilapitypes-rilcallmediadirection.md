---
UID: NE:rilapitypes.RILCALLMEDIADIRECTION
title: RILCALLMEDIADIRECTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediadirection.htm
old-project: netvista
ms.assetid: 8c6b2329-9956-43c1-8a4d-ef9587cf0980
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILCALLMEDIADIRECTION, RILCALLMEDIADIRECTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMEDIADIRECTION_MAX, RIL_CALLMEDIADIRECTION_RX, RIL_CALLMEDIADIRECTION_RXTX, RIL_CALLMEDIADIRECTION_TX, netvista.rilcallmediadirection, ntddrilapitypes/RILCALLMEDIADIRECTION, ntddrilapitypes/RIL_CALLMEDIADIRECTION_MAX, ntddrilapitypes/RIL_CALLMEDIADIRECTION_RX, ntddrilapitypes/RIL_CALLMEDIADIRECTION_RXTX, ntddrilapitypes/RIL_CALLMEDIADIRECTION_TX
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
-	RILCALLMEDIADIRECTION
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIADIRECTION
req.product: Windows 10 or later.
---

# RILCALLMEDIADIRECTION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILCALLMEDIADIRECTION { 
  RIL_CALLMEDIADIRECTION_RX,
  RIL_CALLMEDIADIRECTION_TX,
  RIL_CALLMEDIADIRECTION_RXTX,
  RIL_CALLMEDIADIRECTION_MAX
} RILCALLMEDIADIRECTION;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_RX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_TX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_RXTX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |