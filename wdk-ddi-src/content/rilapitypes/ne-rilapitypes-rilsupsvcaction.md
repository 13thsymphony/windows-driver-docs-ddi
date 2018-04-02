---
UID: NE:rilapitypes.RILSUPSVCACTION
title: RILSUPSVCACTION
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsupsvcaction.htm
old-project: netvista
ms.assetid: 14c9b97d-7f3f-45ef-9be2-c36495c69081
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILSUPSVCACTION, RILSUPSVCACTION enumeration [Network Drivers Starting with Windows Vista], RIL_SUPSVCACTION_DEACTIVATE, RIL_SUPSVCACTION_ERASE, RIL_SUPSVCACTION_INTERROGATE, RIL_SUPSVCACTION_MAX, RIL_SUPSVCACTION_REGISTER, RIL_SUPSVCACTION_REGISTER_PW, RIL_SUPSVCACTION_USSD, netvista.rilsupsvcaction, ntddrilapitypes/RILSUPSVCACTION, ntddrilapitypes/RIL_SUPSVCACTION_DEACTIVATE, ntddrilapitypes/RIL_SUPSVCACTION_ERASE, ntddrilapitypes/RIL_SUPSVCACTION_INTERROGATE, ntddrilapitypes/RIL_SUPSVCACTION_MAX, ntddrilapitypes/RIL_SUPSVCACTION_REGISTER, ntddrilapitypes/RIL_SUPSVCACTION_REGISTER_PW, ntddrilapitypes/RIL_SUPSVCACTION_USSD
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
-	RILSUPSVCACTION
product: Windows
targetos: Windows
req.typenames: RILSUPSVCACTION
req.product: Windows 10 or later.
---

# RILSUPSVCACTION Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILSUPSVCACTION {
  RIL_SUPSVCACTION_ACTIVATE     ,
  RIL_SUPSVCACTION_DEACTIVATE   ,
  RIL_SUPSVCACTION_REGISTER     ,
  RIL_SUPSVCACTION_ERASE        ,
  RIL_SUPSVCACTION_INTERROGATE  ,
  RIL_SUPSVCACTION_REGISTER_PW  ,
  RIL_SUPSVCACTION_USSD         ,
  RIL_SUPSVCACTION_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_SUPSVCACTION_ACTIVATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCACTION_DEACTIVATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCACTION_REGISTER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCACTION_ERASE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCACTION_INTERROGATE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCACTION_REGISTER_PW</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCACTION_USSD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUPSVCACTION_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |