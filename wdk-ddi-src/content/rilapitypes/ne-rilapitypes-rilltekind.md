---
UID: NE:rilapitypes.RILLTEKIND
title: RILLTEKIND
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilltekind.htm
old-project: netvista
ms.assetid: e7457252-0ca9-4cea-bc06-283573e49331
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILLTEKIND, RILLTEKIND enumeration [Network Drivers Starting with Windows Vista], RIL_LTEKIND_FDD, RIL_LTEKIND_FDD_CA, RIL_LTEKIND_MAX, RIL_LTEKIND_RESERVED, RIL_LTEKIND_TDD, RIL_LTEKIND_TDD_CA, RIL_LTEKIND_UNKNOWN_CA, netvista.rilltekind, ntddrilapitypes/RILLTEKIND, ntddrilapitypes/RIL_LTEKIND_FDD, ntddrilapitypes/RIL_LTEKIND_FDD_CA, ntddrilapitypes/RIL_LTEKIND_MAX, ntddrilapitypes/RIL_LTEKIND_RESERVED, ntddrilapitypes/RIL_LTEKIND_TDD, ntddrilapitypes/RIL_LTEKIND_TDD_CA, ntddrilapitypes/RIL_LTEKIND_UNKNOWN_CA
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
-	RILLTEKIND
product: Windows
targetos: Windows
req.typenames: RILLTEKIND
req.product: Windows 10 or later.
---

# RILLTEKIND Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILLTEKIND {
  RIL_LTEKIND_UNKNOWN     ,
  RIL_LTEKIND_FDD         ,
  RIL_LTEKIND_TDD         ,
  RIL_LTEKIND_RESERVED    ,
  RIL_LTEKIND_UNKNOWN_CA  ,
  RIL_LTEKIND_FDD_CA      ,
  RIL_LTEKIND_TDD_CA      ,
  RIL_LTEKIND_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_LTEKIND_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_LTEKIND_FDD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_LTEKIND_TDD</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_LTEKIND_RESERVED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_LTEKIND_UNKNOWN_CA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_LTEKIND_FDD_CA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_LTEKIND_TDD_CA</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_LTEKIND_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |