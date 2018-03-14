---
UID: NE:ntddrilapitypes.RILGETPREFERENCEDOPERATORLISTFORMAT
title: RILGETPREFERENCEDOPERATORLISTFORMAT
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilgetpreferencedoperatorlistformat.htm
old-project: netvista
ms.assetid: 77526649-dc98-4c40-b348-6e5620f6e4eb
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILGETPREFERENCEDOPERATORLISTFORMAT, RILGETPREFERENCEDOPERATORLISTFORMAT enumeration [Network Drivers Starting with Windows Vista], RIL_OPFORMAT_MAX, RIL_OPFORMAT_NUM, RIL_OPFORMAT_SHORT, netvista.rilgetpreferencedoperatorlistformat, ntddrilapitypes/RILGETPREFERENCEDOPERATORLISTFORMAT, ntddrilapitypes/RIL_OPFORMAT_MAX, ntddrilapitypes/RIL_OPFORMAT_NUM, ntddrilapitypes/RIL_OPFORMAT_SHORT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
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
-	RILGETPREFERENCEDOPERATORLISTFORMAT
product: Windows
targetos: Windows
req.typenames: RILGETPREFERENCEDOPERATORLISTFORMAT
---

# RILGETPREFERENCEDOPERATORLISTFORMAT Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILGETPREFERENCEDOPERATORLISTFORMAT { 
  RIL_OPFORMAT_SHORT,
  RIL_OPFORMAT_NUM,
  RIL_OPFORMAT_MAX
} RILGETPREFERENCEDOPERATORLISTFORMAT;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_OPFORMAT_LONG</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_OPFORMAT_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_OPFORMAT_NUM</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_OPFORMAT_SHORT</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |