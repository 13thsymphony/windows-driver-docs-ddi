---
UID: NE:rilapitypes.RILSUBADDRESSTYPE
title: RILSUBADDRESSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddresstype_2.htm
old-project: netvista
ms.assetid: 5484775b-0c02-4879-a550-a4dc99e577ed
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILSUBADDRESSTYPE, RILSUBADDRESSTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_SUBADDRTYPE_MAX, RIL_SUBADDRTYPE_USER, netvista.rilsubaddresstype_2, rilapitypes/RILSUBADDRESSTYPE, rilapitypes/RIL_SUBADDRTYPE_MAX, rilapitypes/RIL_SUBADDRTYPE_USER
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
-	RILSUBADDRESSTYPE
product: Windows
targetos: Windows
req.typenames: RILSUBADDRESSTYPE
req.product: Windows 10 or later.
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
| **Header** | rilapitypes.h |