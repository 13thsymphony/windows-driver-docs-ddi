---
UID: NE:ntddrilapitypes.RILSUBADDRESSTYPE
title: RILSUBADDRESSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddresstype.htm
old-project: netvista
ms.assetid: 18c4f26a-6463-4157-bd81-6bbb2100eff2
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: RILSUBADDRESSTYPE, RILSUBADDRESSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_SUBADDRTYPE_MAX, RIL_SUBADDRTYPE_USER, netvista.rilsubaddresstype, ntddrilapitypes/RILSUBADDRESSTYPE, ntddrilapitypes/RIL_SUBADDRTYPE_MAX, ntddrilapitypes/RIL_SUBADDRTYPE_USER
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
-	RILSUBADDRESSTYPE
product: Windows
targetos: Windows
req.typenames: RILSUBADDRESSTYPE
---

# RILSUBADDRESSTYPE Enumeration
This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.

## Syntax
````
typedef enum _RILSUBADDRESSTYPE { 
  RIL_SUBADDRTYPE_USER,
  RIL_SUBADDRTYPE_MAX
} RILSUBADDRESSTYPE;
````

## Constants

<table>
            
                <tr>
                    <td>RIL_SUBADDRTYPE_MAX</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUBADDRTYPE_NSAP</td>
                    <td></td>
                </tr>
            
                <tr>
                    <td>RIL_SUBADDRTYPE_USER</td>
                    <td></td>
                </tr>
</table>


## Requirements
| &nbsp; | &nbsp; |
| ---- |:---- |
| **Header** | ntddrilapitypes.h (include Rilapitypes.h) |