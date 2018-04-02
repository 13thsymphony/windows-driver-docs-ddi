---
UID: NE:rilapitypes.RILCALLMODIFICATIONINFOMODIFICATIONTYPE
title: RILCALLMODIFICATIONINFOMODIFICATIONTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmodificationinfomodificationtype.htm
old-project: netvista
ms.assetid: 37b18047-7818-4e57-b25a-3c958106e215
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILCALLMODIFICATIONINFOMODIFICATIONTYPE, RILCALLMODIFICATIONINFOMODIFICATIONTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMODIFICATIONTYPE_BLOCKED, RIL_CALLMODIFICATIONTYPE_MAX, RIL_CALLMODIFICATIONTYPE_MODIFIED, netvista.rilcallmodificationinfomodificationtype, ntddrilapitypes/RILCALLMODIFICATIONINFOMODIFICATIONTYPE, ntddrilapitypes/RIL_CALLMODIFICATIONTYPE_BLOCKED, ntddrilapitypes/RIL_CALLMODIFICATIONTYPE_MAX, ntddrilapitypes/RIL_CALLMODIFICATIONTYPE_MODIFIED
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
-	RILCALLMODIFICATIONINFOMODIFICATIONTYPE
product: Windows
targetos: Windows
req.typenames: RILCALLMODIFICATIONINFOMODIFICATIONTYPE
req.product: Windows 10 or later.
---

# RILCALLMODIFICATIONINFOMODIFICATIONTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILCALLMODIFICATIONINFOMODIFICATIONTYPE {
  RIL_CALLMODIFICATIONTYPE_UNKNOWN   ,
  RIL_CALLMODIFICATIONTYPE_BLOCKED   ,
  RIL_CALLMODIFICATIONTYPE_MODIFIED  ,
  RIL_CALLMODIFICATIONTYPE_MAX
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_CALLMODIFICATIONTYPE_UNKNOWN</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMODIFICATIONTYPE_BLOCKED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMODIFICATIONTYPE_MODIFIED</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_CALLMODIFICATIONTYPE_MAX</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |