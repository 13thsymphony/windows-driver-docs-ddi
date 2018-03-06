---
UID: NE:rilapitypes.RILMESSAGEINFOPARAMMASK
title: RILMESSAGEINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinfoparammask_2.htm
old-project: netvista
ms.assetid: 598880f6-0466-4cc1-9f14-3c2e4dda3ba1
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILMESSAGEINFOPARAMMASK, RILMESSAGEINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_MI_ALL, RIL_PARAM_MI_MESSAGE, RIL_PARAM_MI_STATUS, netvista.rilmessageinfoparammask_2, rilapitypes/RILMESSAGEINFOPARAMMASK, rilapitypes/RIL_PARAM_MI_ALL, rilapitypes/RIL_PARAM_MI_MESSAGE, rilapitypes/RIL_PARAM_MI_STATUS
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
-	RILMESSAGEINFOPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILMESSAGEINFOPARAMMASK
req.product: Windows 10 or later.
---

# RILMESSAGEINFOPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMESSAGEINFOPARAMMASK { 
  RIL_PARAM_MI_STATUS,
  RIL_PARAM_MI_MESSAGE,
  RIL_PARAM_MI_ALL
} RILMESSAGEINFOPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_MI_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MI_INDEX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MI_MESSAGE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_MI_STATUS</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |