---
UID: NE:rilapitypes.RILMSGCLASS
title: RILMSGCLASS
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilmsgclass.htm
old-project: netvista
ms.assetid: 2f7e2c4f-56bc-4efd-8911-5161b657dbea
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: RILMSGCLASS, RILMSGCLASS enumeration [Network Drivers Starting with Windows Vista], RIL_MSGCLASS_ALL, RIL_MSGCLASS_BROADCAST, RIL_MSGCLASS_INCOMING, RIL_MSGCLASS_OUTGOING, netvista.rilmsgclass, ntddrilapitypes/RILMSGCLASS, ntddrilapitypes/RIL_MSGCLASS_ALL, ntddrilapitypes/RIL_MSGCLASS_BROADCAST, ntddrilapitypes/RIL_MSGCLASS_INCOMING, ntddrilapitypes/RIL_MSGCLASS_OUTGOING
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
-	RILMSGCLASS
product: Windows
targetos: Windows
req.typenames: RILMSGCLASS
req.product: Windows 10 or later.
---

# RILMSGCLASS Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
```
typedef enum RILMSGCLASS {
  RIL_MSGCLASS_NONE       ,
  RIL_MSGCLASS_INCOMING   ,
  RIL_MSGCLASS_OUTGOING   ,
  RIL_MSGCLASS_BROADCAST  ,
  RIL_MSGCLASS_ALL
} ;
```

## Constants

<table>
            
                <tr>
                    <td>RIL_MSGCLASS_NONE</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCLASS_INCOMING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCLASS_OUTGOING</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCLASS_BROADCAST</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_MSGCLASS_ALL</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | rilapitypes.h (include Rilapitypes.h) |