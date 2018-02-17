---
UID: NE:rilapitypes.RILMESSAGEINFOPARAMMASK
title: RILMESSAGEINFOPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmessageinfoparammask_2.htm
old-project: netvista
ms.assetid: 598880f6-0466-4cc1-9f14-3c2e4dda3ba1
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilmessageinfoparammask_2, RIL_PARAM_MI_STATUS, RIL_PARAM_MI_ALL, RILMESSAGEINFOPARAMMASK enumeration [Network Drivers Starting with Windows Vista], rilapitypes/RIL_PARAM_MI_ALL, RILMESSAGEINFOPARAMMASK, rilapitypes/RIL_PARAM_MI_MESSAGE, RIL_PARAM_MI_MESSAGE, rilapitypes/RILMESSAGEINFOPARAMMASK, rilapitypes/RIL_PARAM_MI_STATUS
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