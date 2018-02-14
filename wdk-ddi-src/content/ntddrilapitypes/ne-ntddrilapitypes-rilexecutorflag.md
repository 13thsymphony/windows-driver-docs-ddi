---
UID: NE:ntddrilapitypes.RILEXECUTORFLAG
title: RILEXECUTORFLAG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorflag.htm
old-project: netvista
ms.assetid: b388a5d9-3549-472d-8ebe-b618751626ed
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilexecutorflag, ntddrilapitypes/RIL_EXECUTORFLAG_ALL, ntddrilapitypes/RILEXECUTORFLAG, RIL_EXECUTORFLAG_ALL, RIL_EXECUTORFLAG_HIGHPRIORITY, ntddrilapitypes/RIL_EXECUTORFLAG_HIGHPRIORITY, RILEXECUTORFLAG enumeration [Network Drivers Starting with Windows Vista], RILEXECUTORFLAG
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
-	RILEXECUTORFLAG
product: Windows
targetos: Windows
req.typenames: RILEXECUTORFLAG
---

# RILEXECUTORFLAG Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILEXECUTORFLAG { 
  RIL_EXECUTORFLAG_HIGHPRIORITY,
  RIL_EXECUTORFLAG_ALL
} RILEXECUTORFLAG;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_EXECUTORFLAG_ALL</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EXECUTORFLAG_ENABLED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_EXECUTORFLAG_HIGHPRIORITY</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h |