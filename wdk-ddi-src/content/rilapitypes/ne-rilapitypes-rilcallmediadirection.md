---
UID: NE:rilapitypes.RILCALLMEDIADIRECTION
title: RILCALLMEDIADIRECTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediadirection_2.htm
old-project: netvista
ms.assetid: fcb5f1a4-8673-412e-95ac-5f3ca781411b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILCALLMEDIADIRECTION, RILCALLMEDIADIRECTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMEDIADIRECTION_MAX, RIL_CALLMEDIADIRECTION_RX, RIL_CALLMEDIADIRECTION_RXTX, RIL_CALLMEDIADIRECTION_TX, netvista.rilcallmediadirection_2, rilapitypes/RILCALLMEDIADIRECTION, rilapitypes/RIL_CALLMEDIADIRECTION_MAX, rilapitypes/RIL_CALLMEDIADIRECTION_RX, rilapitypes/RIL_CALLMEDIADIRECTION_RXTX, rilapitypes/RIL_CALLMEDIADIRECTION_TX
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
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
                    <td>RIL_CALLMEDIADIRECTION_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_RX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_RXTX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMEDIADIRECTION_TX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |