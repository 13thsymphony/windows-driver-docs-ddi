---
UID: NE:rilapitypes.RILRESETMODEMKIND
title: RILRESETMODEMKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilresetmodemkind_2.htm
old-project: netvista
ms.assetid: 622f9629-f172-469c-aba5-50a4eec78ab0
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILRESETMODEMKIND, RILRESETMODEMKIND enumeration [Network Drivers Starting with Windows Vista], RIL_RESETMODEMKIND_ABRUPT, RIL_RESETMODEMKIND_MAX, netvista.rilresetmodemkind_2, rilapitypes/RILRESETMODEMKIND, rilapitypes/RIL_RESETMODEMKIND_ABRUPT, rilapitypes/RIL_RESETMODEMKIND_MAX
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
-	RILRESETMODEMKIND
product: Windows
targetos: Windows
req.typenames: RILRESETMODEMKIND
req.product: Windows 10 or later.
---

# RILRESETMODEMKIND Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILRESETMODEMKIND { 
  RIL_RESETMODEMKIND_ABRUPT,
  RIL_RESETMODEMKIND_MAX
} RILRESETMODEMKIND;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_RESETMODEMKIND_ABRUPT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RESETMODEMKIND_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_RESETMODEMKIND_NORMAL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |