---
UID: NE:rilapitypes.RILMSGDCSALPHABET
title: RILMSGDCSALPHABET
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgdcsalphabet_2.htm
old-project: netvista
ms.assetid: 62cd5dd1-8775-4b60-9aa2-3f8e0a3a4b26
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: RILMSGDCSALPHABET, RILMSGDCSALPHABET enumeration [Network Drivers Starting with Windows Vista], RIL_DCSALPHABET_8BIT, RIL_DCSALPHABET_MAX, RIL_DCSALPHABET_UCS2, netvista.rilmsgdcsalphabet_2, rilapitypes/RILMSGDCSALPHABET, rilapitypes/RIL_DCSALPHABET_8BIT, rilapitypes/RIL_DCSALPHABET_MAX, rilapitypes/RIL_DCSALPHABET_UCS2
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
-	RILMSGDCSALPHABET
product: Windows
targetos: Windows
req.typenames: RILMSGDCSALPHABET
req.product: Windows 10 or later.
---

# RILMSGDCSALPHABET Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILMSGDCSALPHABET { 
  RIL_DCSALPHABET_8BIT,
  RIL_DCSALPHABET_UCS2,
  RIL_DCSALPHABET_MAX
} RILMSGDCSALPHABET;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_DCSALPHABET_8BIT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSALPHABET_DEFAULT</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSALPHABET_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_DCSALPHABET_UCS2</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h |