---
UID: NE:ntddrilapitypes.RIL3GPP2TONE
title: RIL3GPP2TONE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\ril3gpp2tone.htm
old-project: netvista
ms.assetid: bf19de84-1c2d-4e9b-8061-888634dc2147
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RIL3GPP2TONE, RIL3GPP2TONE enumeration [Network Drivers Starting with Windows Vista], RIL_3GPP2TONE_ABRVINTERCEPT, RIL_3GPP2TONE_ABRVREORDER, RIL_3GPP2TONE_ANSWER, RIL_3GPP2TONE_BUSY, RIL_3GPP2TONE_CALLWAITING, RIL_3GPP2TONE_CONFIRM, RIL_3GPP2TONE_DIAL, RIL_3GPP2TONE_INTERCEPT, RIL_3GPP2TONE_MAX, RIL_3GPP2TONE_PIP, RIL_3GPP2TONE_REORDER, RIL_3GPP2TONE_RINGBACK, netvista.ril3gpp2tone, ntddrilapitypes/RIL3GPP2TONE, ntddrilapitypes/RIL_3GPP2TONE_ABRVINTERCEPT, ntddrilapitypes/RIL_3GPP2TONE_ABRVREORDER, ntddrilapitypes/RIL_3GPP2TONE_ANSWER, ntddrilapitypes/RIL_3GPP2TONE_BUSY, ntddrilapitypes/RIL_3GPP2TONE_CALLWAITING, ntddrilapitypes/RIL_3GPP2TONE_CONFIRM, ntddrilapitypes/RIL_3GPP2TONE_DIAL, ntddrilapitypes/RIL_3GPP2TONE_INTERCEPT, ntddrilapitypes/RIL_3GPP2TONE_MAX, ntddrilapitypes/RIL_3GPP2TONE_PIP, ntddrilapitypes/RIL_3GPP2TONE_REORDER, ntddrilapitypes/RIL_3GPP2TONE_RINGBACK
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	RIL3GPP2TONE
product:
- Windows
targetos: Windows
req.typenames: RIL3GPP2TONE
---

# RIL3GPP2TONE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RIL3GPP2TONE {
  RIL_3GPP2TONE_TONEOFF        ,
  RIL_3GPP2TONE_DIAL           ,
  RIL_3GPP2TONE_RINGBACK       ,
  RIL_3GPP2TONE_INTERCEPT      ,
  RIL_3GPP2TONE_ABRVINTERCEPT  ,
  RIL_3GPP2TONE_REORDER        ,
  RIL_3GPP2TONE_ABRVREORDER    ,
  RIL_3GPP2TONE_BUSY           ,
  RIL_3GPP2TONE_CONFIRM        ,
  RIL_3GPP2TONE_ANSWER         ,
  RIL_3GPP2TONE_CALLWAITING    ,
  RIL_3GPP2TONE_PIP            ,
  RIL_3GPP2TONE_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_3GPP2TONE_TONEOFF</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_DIAL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_RINGBACK</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_INTERCEPT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_ABRVINTERCEPT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_REORDER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_ABRVREORDER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_BUSY</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_CONFIRM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_ANSWER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_CALLWAITING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_PIP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_3GPP2TONE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |