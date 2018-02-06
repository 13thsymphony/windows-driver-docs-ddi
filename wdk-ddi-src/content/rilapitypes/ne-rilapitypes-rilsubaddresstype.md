---
UID: NE:rilapitypes.RILSUBADDRESSTYPE
title: RILSUBADDRESSTYPE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsubaddresstype_2.htm
old-project: netvista
ms.assetid: 5484775b-0c02-4879-a550-a4dc99e577ed
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: rilapitypes/RILSUBADDRESSTYPE, rilapitypes/RIL_SUBADDRTYPE_MAX, RIL_SUBADDRTYPE_MAX, netvista.rilsubaddresstype_2, RIL_SUBADDRTYPE_USER, rilapitypes/RIL_SUBADDRTYPE_USER, RILSUBADDRESSTYPE, RILSUBADDRESSTYPE enumeration [Network Drivers Starting with Windows Vista]
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