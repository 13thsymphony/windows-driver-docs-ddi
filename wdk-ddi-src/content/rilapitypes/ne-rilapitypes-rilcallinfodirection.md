---
UID: NE:rilapitypes.RILCALLINFODIRECTION
title: RILCALLINFODIRECTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallinfodirection.htm
old-project: netvista
ms.assetid: 2243fb04-81a9-49d6-9ce2-d06d4a590fb1
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILCALLINFODIRECTION, RILCALLINFODIRECTION enumeration [Network Drivers Starting with Windows Vista], RIL_CALLDIR_MAX, RIL_CALLDIR_OUTGOING, netvista.rilcallinfodirection, ntddrilapitypes/RILCALLINFODIRECTION, ntddrilapitypes/RIL_CALLDIR_MAX, ntddrilapitypes/RIL_CALLDIR_OUTGOING
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
-	RILCALLINFODIRECTION
product:
- Windows
targetos: Windows
req.typenames: RILCALLINFODIRECTION
req.product: Windows 10 or later.
---

# RILCALLINFODIRECTION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILCALLINFODIRECTION {
  RIL_CALLDIR_INCOMING  ,
  RIL_CALLDIR_OUTGOING  ,
  RIL_CALLDIR_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_CALLDIR_INCOMING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLDIR_OUTGOING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLDIR_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |