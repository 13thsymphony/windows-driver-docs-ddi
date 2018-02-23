---
UID: NE:oemrilapitypes.RILGETTOKENPARAMMASK
title: RILGETTOKENPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgettokenparammask.htm
old-project: netvista
ms.assetid: d791b497-3ef3-42f1-a6e6-980992c97f45
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: oemrilapitypes/RIL_PARAM_GETTOKEN_HEADER, oemrilapitypes/RIL_PARAM_GETTOKEN_ALL, oemrilapitypes/RIL_PARAM_GETTOKEN_PROTOCOL_ID, RIL_PARAM_GETTOKEN_ALL, RIL_PARAM_GETTOKEN_HEADER, RILDEVSPECIFICPARAMMASK, netvista.rilgettokenparammask, RILDEVSPECIFICPARAMMASK enumeration [Network Drivers Starting with Windows Vista], oemrilapitypes/RILGETTOKENPARAMMASK, RILGETTOKENPARAMMASK, RIL_PARAM_GETTOKEN_PROTOCOL_ID, RIL_PARAM_GETTOKEN_TIMEOUT, oemrilapitypes/RIL_PARAM_GETTOKEN_TIMEOUT, RILGETTOKENPARAMMASK enumeration [Network Drivers Starting with Windows Vista]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: oemrilapitypes.h
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
req.lib: Ntstrsafe.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	oemrilapitypes.h
apiname:
-	RILDEVSPECIFICPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILDEVSPECIFICPARAMMASK
---

# RILGETTOKENPARAMMASK Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILDEVSPECIFICPARAMMASK { 
  RIL_PARAM_GETTOKEN_TIMEOUT,
  RIL_PARAM_GETTOKEN_HEADER,
  RIL_PARAM_GETTOKEN_PROTOCOL_ID,
  RIL_PARAM_GETTOKEN_ALL
} RILDEVSPECIFICPARAMMASK;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_PARAM_GETTOKEN_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GETTOKEN_HEADER</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GETTOKEN_PROTOCOL_ID</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_PARAM_GETTOKEN_TIMEOUT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | oemrilapitypes.h |