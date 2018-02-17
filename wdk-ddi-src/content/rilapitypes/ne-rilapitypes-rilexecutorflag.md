---
UID: NE:rilapitypes.RILEXECUTORFLAG
title: RILEXECUTORFLAG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorflag_2.htm
old-project: netvista
ms.assetid: 691d962a-5775-462a-8c3f-d9b02e189810
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilexecutorflag_2, RILEXECUTORFLAG enumeration [Network Drivers Starting with Windows Vista], RIL_EXECUTORFLAG_HIGHPRIORITY, rilapitypes/RILEXECUTORFLAG, RILEXECUTORFLAG, RIL_EXECUTORFLAG_ALL, rilapitypes/RIL_EXECUTORFLAG_ALL, rilapitypes/RIL_EXECUTORFLAG_HIGHPRIORITY
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
-	RILEXECUTORFLAG
product: Windows
targetos: Windows
req.typenames: RILEXECUTORFLAG
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |