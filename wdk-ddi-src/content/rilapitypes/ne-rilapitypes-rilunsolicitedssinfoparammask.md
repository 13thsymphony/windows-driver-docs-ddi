---
UID: NE:rilapitypes.RILUNSOLICITEDSSINFOPARAMMASK
title: RILUNSOLICITEDSSINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilunsolicitedssinfoparammask_2.htm
old-project: netvista
ms.assetid: 772b2ab3-6ce6-4303-8b1e-145e4e28ee44
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RIL_PARAM_UNSSS_ADDRESS, rilapitypes/RIL_PARAM_UNSSS_CUGINDEX, RIL_PARAM_UNSSS_ADDRESS, rilapitypes/RIL_PARAM_UNSSS_SUBADDR, rilapitypes/RIL_PARAM_UNSSS_ID, RILUNSOLICITEDSSINFOPARAMMASK, RILUNSOLICITEDSSINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_UNSSS_HISTLENGTH, RIL_PARAM_UNSSS_HISTLENGTH, rilapitypes/RIL_PARAM_UNSSS_HISTINFO, rilapitypes/RIL_PARAM_UNSSS_ALL, netvista.rilunsolicitedssinfoparammask_2, rilapitypes/RILUNSOLICITEDSSINFOPARAMMASK, RIL_PARAM_UNSSS_ID, RIL_PARAM_UNSSS_NOTIFICATIONCODE, RIL_PARAM_UNSSS_SUBADDR, RIL_PARAM_UNSSS_CUGINDEX, RIL_PARAM_UNSSS_ALL, rilapitypes/RIL_PARAM_UNSSS_NOTIFICATIONCODE, RIL_PARAM_UNSSS_HISTINFO
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
-	RILUNSOLICITEDSSINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILUNSOLICITEDSSINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILUNSOLICITEDSSINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILUNSOLICITEDSSINFOPARAMMASK { 
  RIL_PARAM_UNSSS_ID,
  RIL_PARAM_UNSSS_NOTIFICATIONCODE,
  RIL_PARAM_UNSSS_ADDRESS,
  RIL_PARAM_UNSSS_SUBADDR,
  RIL_PARAM_UNSSS_CUGINDEX,
  RIL_PARAM_UNSSS_HISTLENGTH,
  RIL_PARAM_UNSSS_HISTINFO,
  RIL_PARAM_UNSSS_ALL
} RILUNSOLICITEDSSINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_ADDRESS</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_CUGINDEX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_EXECUTOR</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_HISTINFO</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_HISTLENGTH</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_NOTIFICATIONCODE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_UNSSS_SUBADDR</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |